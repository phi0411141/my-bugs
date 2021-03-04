# Decorators
A typesafe version of validator decorators for Class public methods
```ts
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

# Enum
Fake generic for enum
```ts
  export function createYFromEnum<T extends string, TEnumValue extends string | number>(
    enumVal: { [key in T]: TEnumValue }
  ) {
    // function body, now we can pass T as keyof enum and TEnumValue as typeof enum
  }

  // Example usage:
  enum X {
    A = 1;
    B = 2;
  }
  
  createYFromEnum(X);
      
```
