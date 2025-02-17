# TYPESCRIPT SYNTAX REFERENCE (FRONTEND)

## 1. VARIABLES & DATA TYPES
### Purpose: Declaring variables with type safety.
```typescript
let message: string = "Hello, TypeScript";
let count: number = 10;
let isActive: boolean = true;
let numbers: number[] = [1, 2, 3];
let tuple: [string, number] = ["Alice", 30];
let user: object = { name: "John", age: 25 };
let anything: any = "Could be anything";
let unknownType: unknown = "Can be checked later";
```

## 2. FUNCTIONS
### Purpose: Define reusable blocks of code.
```typescript
function greet(name: string): string {
    return `Hello, ${name}`;
}
const sum = (a: number, b: number): number => a + b;
```

## 3. INTERFACES
### Purpose: Define the shape of an object.
```typescript
interface User {
    name: string;
    age: number;
}
let user1: User = { name: "Alice", age: 30 };
```

## 4. CLASSES
### Purpose: Define reusable object structures.
```typescript
class Person {
    name: string;
    constructor(name: string) {
        this.name = name;
    }
    greet(): string {
        return `Hello, my name is ${this.name}`;
    }
}
const person1 = new Person("Alice");
console.log(person1.greet());
```

## 5. GENERICS
### Purpose: Create reusable components that work with multiple types.
```typescript
function identity<T>(arg: T): T {
    return arg;
}
console.log(identity<string>("Hello"));
console.log(identity<number>(42));
```

## 6. ENUMS
### Purpose: Define a set of named constants.
```typescript
enum Color {
    Red, Green, Blue
}
let favoriteColor: Color = Color.Green;
```

## 7. TYPE ALIASES & UNION TYPES
### Purpose: Create custom types and allow multiple types.
```typescript
type ID = string | number;
let userID: ID = 101;
```

## 8. OPTIONAL & READONLY PROPERTIES
### Purpose: Make properties optional or immutable.
```typescript
interface Car {
    brand: string;
    model: string;
    year?: number; // Optional property
    readonly vin: string; // Immutable property
}
```

## 9. REACT SPECIFIC TYPESCRIPT
### Using TypeScript with React Components
```typescript
type ButtonProps = {
    label: string;
    onClick: () => void;
};

const Button: React.FC<ButtonProps> = ({ label, onClick }) => {
    return <button onClick={onClick}>{label}</button>;
};
```

## 10. HOOKS WITH TYPESCRIPT
### Typing useState & useEffect
```typescript
const [count, setCount] = useState<number>(0);

useEffect(() => {
    console.log("Count changed: ", count);
}, [count]);
```

## 11. CONTEXT API WITH TYPESCRIPT
### Creating a context with types
```typescript
interface ThemeContextType {
    theme: string;
    toggleTheme: () => void;
}
const ThemeContext = createContext<ThemeContextType | null>(null);
```

## 12. EVENT HANDLING
### Typing events in React
```typescript
const handleClick = (event: React.MouseEvent<HTMLButtonElement>): void => {
    console.log("Button clicked", event);
};
```

## 13. FORM HANDLING
### Typing form elements
```typescript
const handleInputChange = (event: React.ChangeEvent<HTMLInputElement>) => {
    console.log(event.target.value);
};
```

## 14. FETCH API WITH TYPESCRIPT
### Making API calls with typed responses
```typescript
interface User {
    id: number;
    name: string;
}

const fetchUsers = async (): Promise<User[]> => {
    const response = await fetch("https://api.example.com/users");
    return response.json();
};
```

## 15. ERROR HANDLING
### Using try-catch with type safety
```typescript
try {
    throw new Error("Something went wrong");
} catch (error) {
    if (error instanceof Error) {
        console.error(error.message);
    }
}
```

## 16. SUMMARY TABLE
| FEATURE | USAGE |
|---------|------|
| Variables | `let name: string = "Alice";` |
| Functions | `function add(a: number, b: number): number { return a + b; }` |
| Interfaces | `interface User { name: string; age: number; }` |
| Classes | `class Car { constructor(public model: string) {} }` |
| Generics | `function identity<T>(arg: T): T { return arg; }` |
| Enums | `enum Color { Red, Green, Blue }` |
| React Components | `const Button: React.FC<ButtonProps> = ({ label }) => { return <button>{label}</button>; }` |
| useState Hook | `const [count, setCount] = useState<number>(0);` |
| useEffect Hook | `useEffect(() => { console.log(count); }, [count]);` |
| Fetch API | `const fetchUsers = async (): Promise<User[]> => { ... }` |
| Event Handling | `const handleClick = (event: React.MouseEvent<HTMLButtonElement>) => {}` |

---
This guide covers essential TypeScript concepts for frontend development, particularly with React.
