# TYPESCRIPT SYNTAX REFERENCE

## VARIABLES & DATA TYPES
```typescript
let num: number = 10;
let str: string = "Hello";
let isTrue: boolean = true;
let arr: number[] = [1, 2, 3];
let tuple: [string, number] = ["Age", 25];
let obj: { name: string; age: number } = { name: "John", age: 30 };
let anyVar: any = "Can be anything";
let unknownVar: unknown = 42;
let neverVar: never;
```

## FUNCTIONS
```typescript
function greet(name: string): string {
  return `Hello, ${name}!`;
}
const add = (a: number, b: number): number => a + b;
function logMessage(message: string): void {
  console.log(message);
}
```

## CLASSES & OBJECT-ORIENTED PROGRAMMING
```typescript
class Person {
  constructor(public name: string, private age: number) {}
  greet() {
    return `Hello, my name is ${this.name}`;
  }
}
const john = new Person("John", 30);
```

## INTERFACES
```typescript
interface User {
  id: number;
  name: string;
  email?: string;
}
let user: User = { id: 1, name: "Alice" };
```

## GENERICS
```typescript
function identity<T>(arg: T): T {
  return arg;
}
let numIdentity = identity<number>(42);
```

## ENUMS
```typescript
enum Direction {
  Up,
  Down,
  Left,
  Right
}
let move: Direction = Direction.Up;
```

## TYPE ALIASES & UNION TYPES
```typescript
type ID = string | number;
let userId: ID = 123;
userId = "abc";
```

## TYPE ASSERTIONS
```typescript
let someValue: any = "Hello";
let strLength: number = (someValue as string).length;
```

## MODULES & IMPORT/EXPORT
```typescript
// File: module.ts
export const PI = 3.14;
export function square(x: number): number {
  return x * x;
}

// File: main.ts
import { PI, square } from "./module";
console.log(square(PI));
```

## PROMISES & ASYNC/AWAIT
```typescript
async function fetchData(): Promise<string> {
  return new Promise((resolve) => setTimeout(() => resolve("Data loaded"), 1000));
}
fetchData().then(console.log);
```

## ERROR HANDLING
```typescript
try {
  throw new Error("Something went wrong");
} catch (error) {
  console.error(error.message);
} finally {
  console.log("Cleanup");
}
```

## TYPE UTILITIES
```typescript
type PartialUser = Partial<User>;
type ReadonlyUser = Readonly<User>;
```

## DECORATORS
```typescript
function Log(target: any, propertyKey: string) {
  console.log(`Property ${propertyKey} was accessed`);
}
class Test {
  @Log
  name: string;
}
```

## DOM MANIPULATION
```typescript
const button = document.querySelector("button") as HTMLButtonElement;
button.addEventListener("click", () => alert("Clicked!"));
```

## EVENT LOOP & ASYNC PROGRAMMING
```typescript
console.log("Start");
setTimeout(() => console.log("Timeout"), 0);
Promise.resolve().then(() => console.log("Promise"));
console.log("End");
// Output: Start -> End -> Promise -> Timeout
```

## SUMMARY
| Feature        | Syntax Example |
|---------------|----------------|
| Variable Declaration | `let x: number = 10;` |
| Function Definition | `function add(a: number, b: number): number { return a + b; }` |
| Class | `class Person { constructor(public name: string) {} }` |
| Interface | `interface User { id: number; name: string; }` |
| Generic Function | `function identity<T>(arg: T): T { return arg; }` |
| Enum | `enum Direction { Up, Down, Left, Right }` |
| Async Function | `async function fetchData(): Promise<string> { return "data"; }` |
| Try-Catch | `try { throw new Error("Oops"); } catch (e) { console.log(e); }` |

This serves as a complete TypeScript syntax reference.
