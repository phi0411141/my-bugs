# Decorators
A typesafe version of validator decorators for Class public methods
```
  type AllMethodsOf<T> = {
    [K in keyof T]: T[K] extends (...args: any[]) => any ? K : never;
  }[keyof T];

  export function validator<T, K extends AllMethodsOf<T>>(
      ...fns: ((...args: Parameters<T[K]>) => void)[]
  ) {
      return function(_target: T, _property: K, descriptor: PropertyDescriptor) {
          let originalMethod = descriptor.value;

          //wrapping the original method
          descriptor.value = function(...args: Parameters<T[K]>) {
              if (Array.isArray(fns)) {
                  fns.forEach((fn) => fn(...args));
              }

              return originalMethod;
          };
      };
  }

```
