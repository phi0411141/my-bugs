# mathjax loading extension
  window.MathJax.Ajax.config.path["extensionName"] = "url-to-extension";
    window.MathJax.Ajax.Require("[extensionName]/scriptName.js"); // need to require here
    window.MathJax.Hub.Config({
      tex2jax: {
        inlineMath: [['$', '$'], ["\\(", "\\)"]],
        displayMath: [['$$', '$$'], ["\\[", "\\]"]],
        processEscapes: true
      },
      TeX: {
        extensions: ["[extensionName]/scriptName.js"]
      }
    });
