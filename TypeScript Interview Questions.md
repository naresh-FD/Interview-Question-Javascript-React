# TypeScript Interview Questions for Experienced Developers

## 1. What is TypeScript, and what problem does it solve?

TypeScript is a statically typed superset of JavaScript that adds optional static typing and other
features to the language. It aims to make it easier to write and maintain large-scale JavaScript
applications by catching errors at compile time rather than runtime. TypeScript compiles down to
plain JavaScript, making it compatible with existing JavaScript codebases and environments.

## 2. Explain the benefits of using TypeScript over JavaScript.

- **Static Typing**: TypeScript allows developers to specify types for variables, parameters, return
  values, etc., which helps catch type-related errors early in the development process.
- **Enhanced IDE Support**: TypeScript provides better tooling support, including features like code
  completion, refactoring, and type checking, which can improve developer productivity.
- **Readability and Maintainability**: With type annotations and interfaces, TypeScript code tends
  to be more self-documenting, making it easier to understand and maintain.
- **Better Collaboration**: TypeScript's type system serves as a form of documentation, making it
  easier for teams to collaborate on codebases and understand each other's code.
- **Compatibility**: TypeScript code can be compiled down to various versions of JavaScript,
  ensuring compatibility with different environments and browsers.

## 3. How does TypeScript handle type inference?

TypeScript employs a powerful type inference system that infers types based on context when type
annotations are not explicitly provided. This means TypeScript can often determine the types of
variables, parameters, and return values by analyzing the surrounding code. Type inference helps
reduce the amount of boilerplate code required while still providing type safety.

## 4. What are the key differences between interfaces and types in TypeScript?

- **Interfaces**: Used to define the shape of objects or classes. They can only represent the
  structure of an object and cannot be used to describe primitive types or unions.
- **Types**: More flexible than interfaces. They can represent any valid type in TypeScript,
  including primitives, unions, intersections, and more. Types can also be used to define aliases
  for complex type expressions.

## 5. How does TypeScript handle null and undefined values?

TypeScript has strict null checks enabled by default, which means variables declared without an
explicit type cannot be assigned `null` or `undefined` unless those types are explicitly allowed.
Developers can use union types (`| null | undefined`) or enable the `strictNullChecks` compiler
option to enforce stricter null checking.

## 6. Explain the concept of generics in TypeScript.

Generics in TypeScript allow developers to create reusable components and functions that work with a
variety of data types. They enable the definition of functions, classes, and interfaces that can
operate on a range of types without sacrificing type safety. Generics are indicated by angle
brackets (`<>`) and can be used to define placeholder types for parameters and return values.

## 7. How does TypeScript handle modules, and what are the different module formats it supports?

TypeScript supports various module formats, including CommonJS, AMD, UMD, SystemJS, and ES6 modules.
Modules in TypeScript help organize code by encapsulating related functionality and dependencies.
The `export` and `import` keywords are used to define and consume modules, respectively.
TypeScript's module resolution algorithm determines how module imports are resolved at compile time.

## 8. What is the difference between ambient declarations and regular declarations in TypeScript?

- **Regular Declarations**: Typically found in regular TypeScript source files (.ts files) and are
  used to define types, interfaces, functions, classes, etc., that are part of the codebase.
- **Ambient Declarations**: Used to declare types and interfaces for libraries or APIs that are not
  written in TypeScript. Ambient declarations are usually found in `.d.ts` files and are used to
  provide type information for existing JavaScript code or third-party libraries.

## 9. How can you integrate TypeScript into an existing JavaScript project?

Integrating TypeScript into an existing JavaScript project involves adding a TypeScript
configuration file (`tsconfig.json`), installing the TypeScript compiler (`tsc`), and converting
existing JavaScript files to TypeScript (.ts files) gradually. TypeScript's incremental adoption
allows developers to migrate to TypeScript at their own pace, converting files one by one and
leveraging type checking and other TypeScript features as needed.

## 10. Explain the concept of decorators in TypeScript and provide an example of their usage.

Decorators are a feature of TypeScript used to annotate and modify classes, methods, properties, or
parameters at design time. They provide a way to add metadata or behavior to code without modifying
its underlying structure. Decorators are indicated by the `@` symbol followed by the decorator
function name and can accept arguments. Decorators are commonly used in frameworks like Angular for
defining component metadata, route configurations, etc.

Example:

```typescript
function log(target: any, key: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value;

  descriptor.value = function (...args: any[]) {
    console.log(`Calling ${key} with arguments: ${JSON.stringify(args)}`);
    const result = originalMethod.apply(this, args);
    console.log(`Result of ${key}: ${JSON.stringify(result)}`);
    return result;
  };

  return descriptor;
}

class Calculator {
  @log
  add(x: number, y: number) {
    return x + y;
  }
}

const calc = new Calculator();
calc.add(2, 3); // Output: Calling add with arguments: [2,3] \n Result of add: 5
```
