# TypeScript Interview Questions Explained

## 1. What are some differences between interfaces and types in TypeScript?

Both `interfaces` and `type` aliases are used to define custom types in TypeScript, but they have some key differences:

| Feature                | Interface | Type Alias |
|------------------------|-----------|------------|
| Extensibility          | Can be extended using `extends` | Cannot be extended |
| Implementation         | Can be implemented by classes | Cannot be implemented |
| Union/Intersection     | Cannot represent union types | Can represent unions (`|`) and intersections (`&`) |
| Declaration Merging    | Supports merging of same-name declarations | Doesn't support merging |
| Tuple Types            | Possible but less common | More commonly used for tuples |

**When to use which:**
- Use `interfaces` for object shapes and when you need declaration merging
- Use `type` for unions, intersections, or when you need to define aliases for primitive types

**Example:**
```typescript
// Interface
interface Person {
  name: string;
  age: number;
}

// Type alias
type Point = {
  x: number;
  y: number;
};

// Union type (only possible with type)
type ID = string | number;