# Mathjax loading extension
  window.MathJax.Ajax.config.path["extensionName"] = "url-to-extension"<br>
  window.MathJax.Ajax.Require("[extensionName]/scriptName.js"); // need to require here <br>
  window.MathJax.Hub.Config({<br>
      tex2jax: {<br>
        inlineMath: [['$', '$'], ["\\(", "\\)"]],<br>
        displayMath: [['$$', '$$'], ["\\[", "\\]"]],<br>
        processEscapes: true<br>
      },<br>
      TeX: {<br>
        extensions: ["[extensionName]/scriptName.js"]<br>
      }<br>
    });

# Mathjax initial typeset
 Mathjax will typeset all page when initial, pass skipStartupTypeset: false to config to disable it
