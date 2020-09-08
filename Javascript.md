### Invoke a window function through intermediaries
Example error: `Illegal invocation`
Usually cause by assign a window function to another object, then call the function, which made the window function to loose its internal context
Fix:
From: 
```js
   let obj = {
      get: localStorage.getItem,
      set: localStorage.setItem
   }
```
To:
```js
  let obj= {
     get: (key)=>localStorage.getItem(key),
     set: (key, newVal)=>localStorage.setItem(key, newVal)
  }
```
