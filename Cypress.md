### How to set up cypress with typescript (cypress >4.4)

1. With folder structure bellow
  ```
    project
    │   tsconfig.json
    |   cypress.json
    │
    └───src
    │   │   x.txt
    │   │   y.txt
    │   │
    │   └─── ...
    │   
    └───test
        │___cypress
        |   |
        |   |__plugin
        |   |  |__index.js
        |   |   
        |   |__integration
        |   |
        |   |__..
        |
        │___...
  ```

2. `cypress/plugin/index.js`
  ```js
    const cucumber = require('cypress-cucumber-preprocessor').default;
    const browserify = require("@cypress/browserify-preprocessor");
    
    module.exports = (on, config) => {
      const options = browserify.defaultOptions;

      options.browserifyOptions.plugin.unshift(['tsify', {project: 'test/cypress/tsconfig.json'}]);

      on("file:preprocessor", cucumber(options));
    }
  ```
3. Example `tsconfig.json`
  ```json
    {
      "compilerOptions": {
        "target": "ES2018",
        "module": "ESNext",
        "moduleResolution": "node",
        "lib": [
          "ESNext",
          "ESNext.AsyncIterable",
          "DOM"
        ],
        "esModuleInterop": true,
        "allowJs": true,
        "sourceMap": true,
        "strict": true,
        "noEmit": true,
        "experimentalDecorators": true,
        "importHelpers": true,
        "baseUrl": ".",
        "paths": {
          "~/*": [
            "./src/*"
          ],
          "@/*": [
            "./*"
          ]
        },
        "types": [          
          "cypress",
          "cypress-cucumber-preprocessor"
        ]
      },     
    }
  ```
  
  4. `cypress.json`
  ```json
    {
      "fixturesFolder": "test/cypress/fixtures",
      "integrationFolder": "test/cypress/integration",
      "pluginsFile": "test/cypress/plugins/index.js",
      "screenshotsFolder": "test/cypress/screenshots",
      "videosFolder": "test/cypress/videos",
      "supportFile": "test/cypress/support/index.js",
      "testFiles": "**/*.{feature,features}",
      "baseUrl": "<your desired url>",
      "ignoreTestFiles": "*.ts"
    }
  ```
  5. `package.json`
  ```json
    "cypress-cucumber-preprocessor": {
      "nonGlobalStepDefinitions": true,
      "stepDefinitions": "test/cypress/integration"
    }
  ```
