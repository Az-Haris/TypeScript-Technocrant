# 🎯 TypeScript Interview Questions – Explained Simply

TypeScript is gaining popularity for its ability to enhance JavaScript with static types, making code more robust and easier to maintain. In this blog post, we’ll break down **two essential TypeScript interview questions** in an easy-to-understand format.

---

## 📘 Question 1: What Are Some Differences Between `interface` and `type` in TypeScript?

### 🧠 TL;DR
Both `interface` and `type` are used to define the **shape of an object**, but they have some **key differences** in flexibility and usage.

### ✅ Interface
```ts
interface User {
  name: string;
  age: number;
}
Designed specifically for objects.

Supports declaration merging (can be extended multiple times).

Can extend other interfaces and even types.

✅ Type Alias
ts
Copy
Edit
type User = {
  name: string;
  age: number;
};
Can define unions, intersections, tuples, and primitives too.

No merging — once declared, it can’t be redefined.

Slightly more versatile than interface.

🔄 Comparison Table
Feature	interface ✅	type ✅
Object Shape	✔️	✔️
Declaration Merging	✔️	❌
Extend with extends	✔️	✔️ (limited)
Union/Intersection	❌	✔️
Tuples & Primitives	❌	✔️

💡 Tip
Use interface for class and object structure, and type for complex combinations like unions or tuples.

🔑 Question 2: What Is the Use of keyof in TypeScript?
🧠 TL;DR
The keyof keyword returns a union of all keys of a given object type — making it super handy for building safe, dynamic functions.

📦 Example
ts
Copy
Edit
type User = {
  name: string;
  age: number;
};

type UserKeys = keyof User;  // "name" | "age"
🧰 Practical Use Case
You want a function that accepts only a valid key of a user object:

ts
Copy
Edit
function getValue<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const user = { name: "Alice", age: 30 };

const name = getValue(user, "name"); // ✅ Type: string
const age = getValue(user, "age");   // ✅ Type: number
// getValue(user, "email");          // ❌ Error: "email" is not a key of user
🔐 Why It’s Powerful
Enforces type safety.

Prevents typos in key names.

Allows you to write generic, reusable functions.

📌 Summary
Feature	Description
interface vs type	interface is ideal for objects; type is more flexible (supports unions, primitives, etc.)
keyof	Extracts key names from an object type as a union — great for safe dynamic access

📘 More Interview Topics You Can Explore
What is type inference and how it helps reduce boilerplate?

Differences between any, unknown, and never.

How enums simplify constant management.

Using union and intersection types with real-world examples.

How TypeScript improves project maintainability in large teams.

🧑‍💻 Stay tuned for more beginner-friendly blog posts like this!
Happy Coding 🚀
