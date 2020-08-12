### Nuxt project typescript move srcDir to src/ instead of ./ causing problem in vue typing system. (Cannot find module x or it corresponding type definition)

- Add "include" property to root ts-config.json which include:
  - vue-shim.d.ts 
  ```ts
    declare module '*.vue' {
      import Vue from 'vue'

      export default Vue
    }
  ```
