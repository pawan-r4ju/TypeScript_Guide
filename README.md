# Every Possible Topic in TypeScript

| Category                  | Topic                                      | Syntax                                                                 |
|---------------------------|--------------------------------------------|------------------------------------------------------------------------|
| **Basic Concepts**        | Variables and Data Types                   | `let x: number = 10; const y: string = "hello"; var z: boolean = true;`|
|                           | Primitive Types                            | `string, number, boolean, null, undefined, symbol, bigint`             |
|                           | Complex Types                              | `object, array, tuple`                                                 |
|                           | Special Types                              | `any, void, never, unknown`                                            |
|                           | Type Annotations                           | `let explicitString: string = "TypeScript";`                           |
|                           | Type Assertion                             | `(value as string).length; (<string>value).length;`                    |
|                           | Union Types                                | `let union: string | number = "hello";`                                |
|                           | Intersection Types                         | `type C = A & B;`                                                      |
|                           | Literal Types                              | `let direction: "left" | "right" = "left";`                            |
|                           | Enums                                      | `enum Color { Red = 1, Green, Blue };`                                 |
| **Advanced Types**        | Type Aliases                               | `type StringOrNumber = string | number;`                               |
|                           | Interfaces                                 | `interface User { id: number; name: string; }`                         |
|                           | Mapped Types                               | `type Partial<T> = { [P in keyof T]?: T[P]; };`                        |
|                           | Conditional Types                          | `type TypeName<T> = T extends string ? "string" : "other";`            |
|                           | Utility Types                              | `Partial<T>, Required<T>, Readonly<T>, Pick<T, K>, Omit<T, K>`         |
|                           | Template Literal Types                     | `type Greeting = \`hello ${World}\`;`                                  |
|                           | Keyof Operator                             | `type Keys = keyof SomeType;`                                          |
|                           | Indexed Access Types                       | `type Age = Person["age"];`                                            |
| **Functions**             | Function Declarations                      | `function add(a: number, b: number): number { return a + b; }`         |
|                           | Function Parameters                        | `(a: number, b?: number, ...rest: number[])`                           |
|                           | Return Types                               | `function log(): void { console.log("No return"); }`                   |
|                           | Function Overloads                         | `function pick(arg: string): string; function pick(arg: number): number;` |
|                           | Generics                                   | `function identity<T>(arg: T): T { return arg; }`                      |
|                           | Callable Interfaces                        | `interface CallMe { (name: string): void; }`                           |
| **Classes**               | Class Basics                               | `class Animal { constructor(public name: string) {} }`                 |
|                           | Access Modifiers                           | `private, protected, public, readonly`                                 |
|                           | Inheritance                                | `class Dog extends Animal { bark() { console.log("Woof!"); } }`        |
|                           | Abstract Classes                           | `abstract class Shape { abstract area(): number; }`                   |
|                           | Static Members                             | `static count: number = 0;`                                            |
|                           | Decorators                                 | `@sealed class MyClass {}`                                             |
| **Modules**               | Exporting and Importing                    | `export const x = 10; import { x } from './module';`                   |
|                           | Module Resolution                          | `import * as Utils from './utils';`                                    |
|                           | Namespaces                                 | `namespace Validation { export interface Validator {} }`              |
| **Control Flow Analysis** | Type Guards                                | `if (typeof value === "string") { ... }`                               |
|                           | Narrowing                                  | `if ("swim" in pet) { pet.swim(); }`                                   |
|                           | Exhaustiveness Checking                    | `const exhaustiveCheck: never = value;`                                |
| **Asynchronous Programming** | Promises                                | `Promise.resolve(42).then(value => console.log(value));`               |
|                           | Async/Await                                | `async function fetchData() { const data = await fetch(url); }`        |
| **Tooling and Configuration** | tsconfig.json                          | `{ "compilerOptions": { "target": "ES6", "strict": true } }`           |
|                           | TypeScript Compiler (tsc)                  | `tsc --watch`                                                          |
|                           | Linting and Formatting                     | `eslint --ext .ts,.tsx`                                                |
| **Advanced Features**     | Type Inference                             | `let x = 10; // inferred as number`                                    |
|                           | Type Compatibility                         | `type Subtype = { a: number } & { b: string };`                        |
|                           | Type Widening and Narrowing                | `let value = "hello"; // widened to string`                            |
|                           | Top Types and Bottom Types                 | `any, unknown, never`                                                  |
|                           | Assertion Functions                        | `function assert(condition: any): asserts condition { ... }`          |
|                           | Symbol Types                               | `const uniqueKey = Symbol("unique");`                                  |
|                           | BigInt                                     | `let bigNumber: bigint = BigInt(9007199254740991);`                    |
| **Interoperability**      | TypeScript with JavaScript                 | `declare module "my-js-library" { export function doSomething(): void; }` |
|                           | Third-Party Libraries                      | `npm install @types/lodash`                                            |
|                           | TypeScript with Frameworks                 | React: `const element = <div>Hello</div>;`                             |
| **Performance Optimization** | Tree Shaking                           | `export function usefulFunction() {}`                                  |
|                           | Lazy Loading                               | `import('module').then(module => module.doSomething());`               |
|                           | Minification                               | Use tools like Webpack or Rollup                                       |
| **Debugging and Testing** | Debugging                                  | Use source maps: `"sourceMap": true`                                   |
|                           | Testing                                    | Jest: `test('adds 1 + 2', () => expect(add(1, 2)).toBe(3));`            |

---
# Every Possible Topic in TypeScript

## 1. Basic Concepts

### Variables and Data Types

#### `let`, `const`, `var`
- **Explanation**: `let` and `const` are block-scoped, while `var` is function-scoped.
- **Example**:
  ```typescript
  let x = 10; // Mutable variable
  const y = 20; // Immutable variable
  var z = 30; // Function-scoped
  ```

#### Primitive Types: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`
- **Explanation**: These are the basic building blocks of TypeScript.
- **Example**:
  ```typescript
  let name: string = "John";
  let age: number = 30;
  let isActive: boolean = true;
  let nullable: null = null;
  let notDefined: undefined = undefined;
  let uniqueKey: symbol = Symbol("unique");
  let bigNumber: bigint = BigInt(9007199254740991);
  ```

#### Complex Types: `object`, `array`, `tuple`
- **Explanation**: Objects, arrays, and tuples allow you to work with collections of data.
- **Example**:
  ```typescript
  let person: object = { name: "John", age: 30 };
  let numbers: number[] = [1, 2, 3];
  let tuple: [string, number] = ["hello", 10];
  ```

#### Special Types: `any`, `void`, `never`, `unknown`
- **Explanation**: These types handle special cases like dynamic typing (`any`), no return value (`void`), impossible values (`never`), and unknown types (`unknown`).
- **Example**:
  ```typescript
  let dynamic: any = "can be anything";
  function log(): void {
    console.log("No return value");
  }
  function throwError(): never {
    throw new Error("This function never returns");
  }
  let unknownValue: unknown = "could be anything";
  ```

---

### Type Annotations
#### Explicit Type Annotations
- **Explanation**: Manually specify the type of a variable.
- **Example**:
  ```typescript
  let explicitString: string = "TypeScript";
  ```

#### Implicit Type Inference
- **Explanation**: TypeScript automatically infers the type based on the assigned value.
- **Example**:
  ```typescript
  let inferredString = "Inferred as string";
  ```

---

### Type Assertion
#### `as` Syntax
- **Explanation**: Cast a value to a specific type.
- **Example**:
  ```typescript
  let someValue: any = "this is a string";
  let strLength: number = (someValue as string).length;
  ```

#### Angle-Bracket Syntax (`<type>`)
- **Explanation**: Alternative syntax for type assertion.
- **Example**:
  ```typescript
  let strLengthAlt: number = (<string>someValue).length;
  ```

---

### Union and Intersection Types
#### Union Types (`|`)
- **Explanation**: A variable can hold one of several types.
- **Example**:
  ```typescript
  let union: string | number = "hello";
  union = 42;
  ```

#### Intersection Types (`&`)
- **Explanation**: Combine multiple types into one.
- **Example**:
  ```typescript
  type A = { a: number };
  type B = { b: string };
  type C = A & B;

  let obj: C = { a: 1, b: "hello" };
  ```

---

### Literal Types
#### String Literals
- **Explanation**: Restrict a variable to specific string values.
- **Example**:
  ```typescript
  let direction: "left" | "right" = "left";
  ```

#### Numeric Literals
- **Explanation**: Restrict a variable to specific numeric values.
- **Example**:
  ```typescript
  let diceRoll: 1 | 2 | 3 | 4 | 5 | 6 = 3;
  ```

#### Boolean Literals
- **Explanation**: Restrict a variable to `true` or `false`.
- **Example**:
  ```typescript
  let isDone: true = true;
  ```

---

### Enums
#### Numeric Enums
- **Explanation**: Enumerations with numeric values.
- **Example**:
  ```typescript
  enum Direction {
    Up = 1,
    Down,
    Left,
    Right,
  }
  ```

#### String Enums
- **Explanation**: Enumerations with string values.
- **Example**:
  ```typescript
  enum Direction {
    Up = "UP",
    Down = "DOWN",
    Left = "LEFT",
    Right = "RIGHT",
  }
  ```

#### Reverse Mappings
- **Explanation**: Accessing the key from the value.
- **Example**:
  ```typescript
  enum Enum {
    A,
  }
  let nameOfA = Enum[Enum.A]; // "A"
  ```

---

## 2. Advanced Types

### Type Aliases
- **Explanation**: Create reusable types with `type`.
- **Example**:
  ```typescript
  type StringOrNumber = string | number;
  let value: StringOrNumber = "hello";
  ```

---

### Interfaces
#### Defining Object Shapes
- **Explanation**: Define the structure of an object.
- **Example**:
  ```typescript
  interface User {
    id: number;
    name: string;
  }
  ```

#### Optional Properties
- **Explanation**: Properties that may or may not exist.
- **Example**:
  ```typescript
  interface User {
    id: number;
    name?: string;
  }
  ```

#### Readonly Properties
- **Explanation**: Properties that cannot be modified.
- **Example**:
  ```typescript
  interface User {
    readonly id: number;
  }
  ```

---

### Mapped Types
- **Explanation**: Transform existing types.
- **Example**:
  ```typescript
  type Partial<T> = {
    [P in keyof T]?: T[P];
  };

  interface Todo {
    title: string;
    description: string;
  }

  type PartialTodo = Partial<Todo>;
  ```

---

### Conditional Types
- **Explanation**: Types that depend on conditions.
- **Example**:
  ```typescript
  type TypeName<T> = T extends string ? "string" : "other";
  ```

---

### Utility Types
- **Explanation**: Built-in utility types for common transformations.
- **Example**:
  ```typescript
  type PartialUser = Partial<User>;
  type RequiredUser = Required<User>;
  ```

---

## 3. Functions

### Function Declarations
- **Explanation**: Named, anonymous, and arrow functions.
- **Example**:
  ```typescript
  function add(a: number, b: number): number {
    return a + b;
  }

  const subtract = (a: number, b: number): number => a - b;
  ```

---

### Generics
- **Explanation**: Functions that work with any type.
- **Example**:
  ```typescript
  function identity<T>(arg: T): T {
    return arg;
  }
  ```

---

## 4. Classes

### Class Basics
- **Explanation**: Define classes with properties and methods.
- **Example**:
  ```typescript
  class Animal {
    name: string;

    constructor(name: string) {
      this.name = name;
    }

    move(distance: number): void {
      console.log(`${this.name} moved ${distance}m.`);
    }
  }
  ```

---

### Access Modifiers
- **Explanation**: Control access to class members.
- **Example**:
  ```typescript
  class Animal {
    private name: string;
    protected age: number;

    constructor(name: string, age: number) {
      this.name = name;
      this.age = age;
    }
  }
  ```

---

## 5. Modules

### Exporting and Importing
- **Explanation**: Share code between files.
- **Example**:
  ```typescript
  // math.ts
  export function add(a: number, b: number): number {
    return a + b;
  }

  // app.ts
  import { add } from './math';
  console.log(add(1, 2));
  ```

---

## 6. Control Flow Analysis

### Type Guards
- **Explanation**: Narrow types using `typeof`, `instanceof`, or custom guards.
- **Example**:
  ```typescript
  function isString(value: any): value is string {
    return typeof value === "string";
  }
  ```

---

## 7. Asynchronous Programming

### Async/Await
- **Explanation**: Handle asynchronous operations.
- **Example**:
  ```typescript
  async function fetchData(url: string): Promise<any> {
    const response = await fetch(url);
    return response.json();
  }
  ```

---

## 8. Tooling and Configuration

### tsconfig.json
- **Explanation**: Configure TypeScript compiler options.
- **Example**:
  ```json
  {
    "compilerOptions": {
      "target": "ES6",
      "module": "commonjs",
      "strict": true
    }
  }
  ```

---

## 9. Advanced Features

### Template Literal Types
- **Explanation**: Dynamically create string-based types.
- **Example**:
  ```typescript
  type World = "world";
  type Greeting = `hello ${World}`;
  ```

---

## 10. Interoperability

### TypeScript with JavaScript
- **Explanation**: Gradual migration using `.d.ts` files.
- **Example**:
  ```typescript
  declare module "my-js-library" {
    export function doSomething(): void;
  }
  ```

---

## 11. Performance Optimization

### Tree Shaking
- **Explanation**: Remove unused code during bundling.
- **Example**:
  ```typescript
  // Use ES6 modules for tree shaking
  export function usefulFunction() {}
  ```

---

## 12. Debugging and Testing

### Debugging
- **Explanation**: Use source maps for debugging.
- **Example**:
  ```json
  {
    "compilerOptions": {
      "sourceMap": true
    }
  }
  ```

---

### Testing
- **Explanation**: Write unit tests with Jest.
- **Example**:
  ```typescript
  test("adds 1 + 2 to equal 3", () => {
    expect(add(1, 2)).toBe(3);
  });
  ```

---
check fullstack guide folder