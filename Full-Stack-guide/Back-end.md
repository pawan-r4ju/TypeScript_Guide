# TYPESCRIPT SYNTAX REFERENCE FOR BACKEND DEVELOPMENT

## VARIABLES AND DATA TYPES
```typescript
let name: string = "John";
const age: number = 30;
let isActive: boolean = true;
let skills: string[] = ["TypeScript", "Node.js"];
let user: { id: number; name: string } = { id: 1, name: "Alice" };
```

## FUNCTIONS
```typescript
function add(a: number, b: number): number {
  return a + b;
}

const multiply = (a: number, b: number): number => a * b;
```

## CLASSES
```typescript
class User {
  private id: number;
  public name: string;

  constructor(id: number, name: string) {
    this.id = id;
    this.name = name;
  }

  getDetails(): string {
    return `ID: ${this.id}, Name: ${this.name}`;
  }
}

const user1 = new User(1, "Alice");
console.log(user1.getDetails());
```

## INTERFACES
```typescript
interface Employee {
  id: number;
  name: string;
  department?: string; // Optional property
}

const emp: Employee = { id: 1, name: "Bob" };
```

## ENUMS
```typescript
enum Role {
  ADMIN,
  USER,
  GUEST,
}
let userRole: Role = Role.ADMIN;
```

## MODULES AND IMPORT/EXPORT
```typescript
// user.ts
export class User {
  constructor(public id: number, public name: string) {}
}

// main.ts
import { User } from "./user";
const newUser = new User(2, "Charlie");
```

## ASYNC/AWAIT & PROMISES
```typescript
async function fetchData(): Promise<string> {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Data received"), 2000);
  });
}

fetchData().then((data) => console.log(data));
```

## ERROR HANDLING
```typescript
try {
  throw new Error("Something went wrong");
} catch (error) {
  console.error(error.message);
} finally {
  console.log("Cleanup actions");
}
```

## NODE.JS EXPRESS SERVER
```typescript
import express, { Request, Response } from "express";

const app = express();
app.use(express.json());

app.get("/", (req: Request, res: Response) => {
  res.send("Hello, TypeScript with Node.js!");
});

app.listen(3000, () => {
  console.log("Server running on port 3000");
});
```

## DATABASE CONNECTION (MONGODB EXAMPLE)
```typescript
import mongoose from "mongoose";

mongoose.connect("mongodb://localhost:27017/mydb", { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => console.log("Connected to MongoDB"))
  .catch((err) => console.error("Error connecting to DB", err));
```

## GENERICS
```typescript
function identity<T>(arg: T): T {
  return arg;
}

console.log(identity<number>(10));
console.log(identity<string>("Hello"));
```

## DECORATORS (USED IN NESTJS)
```typescript
function Log(target: any, key: string) {
  console.log(`${key} was called`);
}

class Demo {
  @Log
  greet() {
    console.log("Hello");
  }
}
```

## SUMMARY TABLE

| FEATURE            | SYNTAX EXAMPLE |
|--------------------|---------------|
| **Variables**      | `let name: string = "John";` |
| **Functions**      | `function add(a: number, b: number): number { return a + b; }` |
| **Arrow Functions** | `const multiply = (a: number, b: number): number => a * b;` |
| **Classes**        | `class User { constructor(public id: number, public name: string) {} }` |
| **Interfaces**     | `interface Employee { id: number; name: string; department?: string; }` |
| **Enums**         | `enum Role { ADMIN, USER, GUEST }` |
| **Modules**        | `export class User { ... }` (in `user.ts`), `import { User } from "./user";` (in `main.ts`) |
| **Async/Await**    | `async function fetchData(): Promise<string> { return "Data"; }` |
| **Error Handling** | `try { throw new Error("Error!"); } catch (err) { console.log(err.message); }` |
| **Express Server** | `app.get("/", (req, res) => res.send("Hello!"));` |
| **MongoDB Connection** | `mongoose.connect("mongodb://localhost:27017/mydb")` |
| **Generics**       | `function identity<T>(arg: T): T { return arg; }` |
| **Decorators**     | `@Log greet() { console.log("Hello"); }` |

This reference covers the key TypeScript features used in backend development with Node.js, Express, and MongoDB.
