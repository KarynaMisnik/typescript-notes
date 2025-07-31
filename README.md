# typescript-notes

## Menu

- [The Backstory](#the-backstory)
- [How TS runs](#how-ts-runs)

* [Type System Design in TypeScript](#type-system-design-in-typescript)

## The Backstory

TypeScript was created by Microsoft, led by **<a href='https://en.wikipedia.org/wiki/Anders_Hejlsberg'>Anders Hejlsberg</a>**, who also created:

<ul>
<li>Turbo Pascal (1983)</li>
<li>Delphi (1995)</li>
<li>Was the chief architect of C# at Microsoft</li>
</ul>
 
He's deeply experienced in building programming languages — especially those that combine strong typing with developer productivity.

📅 When was TypeScript released?

<ul>
  <li>Announced: October 2012</li>
  <li>Open-sourced: Same time, under Apache License 2.0</li>
  <li>1.0 release: April 2014</li>
</ul>

❓ Why was TypeScript created?

🚨 The core problem: JavaScript wasn't scaling well

By the late 2000s–early 2010s:

<ul>
  <li>JS was being used for larger, more complex apps (like SPAs and cross-platform apps)</li>
  <li>Teams were struggling with maintainability</li>
  <li>There was no type system, making large codebases brittle</li>
  <li>Refactoring was dangerous and hard</li>
  <li>Code editors had limited ability to help (no IntelliSense, no good autocomplete)</li>
</ul>

Microsoft was building large web-based tools like Visual Studio Online, and they needed a better JavaScript.

🎯 TypeScript’s Goals (original design)

Add static types to JavaScript: So you can catch errors before running code

Be a superset of JavaScript: Any JS file should be valid TypeScript

Support modern JavaScript features: Even before browsers did (e.g. ES6 modules, classes)

Enable tooling: Powerful autocompletion, go-to-definition, refactoring

So it’s not a new language from scratch — it’s more like JavaScript++ with safety, structure, and tooling built in.

🤝 TypeScript vs JavaScript

| Feature              | JavaScript                 | TypeScript                                     |
| -------------------- | -------------------------- | ---------------------------------------------- |
| Type System          | Dynamic (no static types)  | Static typing (optional, via type annotations) |
| Compilation          | Interpreted by browsers    | Compiled to JavaScript                         |
| Tooling Support      | Basic                      | Advanced (IntelliSense, refactoring, etc.)     |
| Error Checking       | Runtime only               | Compile-time and runtime                       |
| Modern JS Features   | ES6+ (depends on engine)   | Supports latest features, even before browsers |
| Adoption             | Universal                  | Growing, especially for large projects         |
| Learning Curve       | Lower                      | Slightly higher (due to types)                 |
| Code Maintainability | Harder for large codebases | Easier, especially for teams                   |

📈 Today

<ul>
  <li>Used by &gt;90% of professional JS developers (State of JS 2023)</li>
  <li>Backed by Microsoft but developed in the open on GitHub</li>
  <li>Powers major frameworks:
    <ul>
      <li>Angular (built with TS)</li>
      <li>React + Vue (heavily support TS)</li>
    </ul>
  </li>
  <li>Enables modern tools like:
    <ul>
      <li>VS Code (built in TS)</li>
      <li>Deno (TS-native runtime)</li>
      <li>SvelteKit, Next.js, etc.</li>
    </ul>
  </li>
</ul>

🧠 Summary

TypeScript was created by Anders Hejlsberg at Microsoft in 2012 to solve theproblem of JavaScript not scaling well for large applications. It adds optionalstatic typing, tooling support, and modern features while staying compatible withJavaScript. It's now a core part of the modern web development stack.

## How TS runs

🧠 First: TypeScript Is Not a Runtime Language

TypeScript doesn’t run — it transpiles to JavaScript, which does run.

🚦 The Lifecycle of a TypeScript File

Step 1: You write TypeScript

```ts
function add(a: number, b: number): number {
  return a + b;
}
```

Step 2: TypeScript Compiler (tsc) checks your code

It parses the file into an **Abstract Syntax Tree (AST)**

It type-checks that your code is valid:

Are <code>a</code> and <code>b</code> numbers?

Does the return type match?

If there’s a problem, it reports at compile time

If not, it moves on to...

Step 3: Transpilation to JavaScript

```ts
function add(a, b) {
  return a + b;
}
```

The type annotations are completely removed. They are only for your development-time safety and clarity.

This JavaScript is what’s actually run by the JS engine (V8, SpiderMonkey, etc.)

⚙️ TypeScript vs JavaScript Engine

| Concern                               | TypeScript handles        | JavaScript engine handles |
| ------------------------------------- | ------------------------- | ------------------------- |
| Type checking                         | ✅                        | ❌                        |
| Type annotations                      | ✅ (strips them)          | ❌                        |
| Transpilation                         | ✅                        | ❌                        |
| Runtime execution                     | ❌                        | ✅                        |
| Error reporting                       | Compile-time              | Runtime only              |
| Modern JS features support            | ✅ (even before browsers) | ✅                        |
| Memory management, garbage collection | ❌                        | ✅                        |

So TypeScript is a compile-time helper. It makes sure your code is more likely to work at runtime, but it has no presence at runtime.

🧰 What Does the TypeScript Compiler (tsc) Do?

The compiler does 3 main things:

Parsing – turns your <code>.ts</code> file into a syntax tree

Type checking – uses the TS type system to validate your code

Emitting JavaScript – produces <code>.js</code> output that removes all TS-specific syntax

🧪 What Makes TS Powerful?

Structural typing (aka "duck typing"): TS types are based on shape, not classes

Type inference: You don’t have to annotate everything — TS infers from usage

Generics: Add type-safe flexibility to your functions and components

Control Flow Analysis: TS can track how types change through conditions:

```ts
function print(x: string | number) {
  if (typeof x === "string") {
    // here x is narrowed to string
  }
}
```

## Type System Design in TypeScript

💡 What Are Types?

A type is a description of what a value is allowed to be.
TypeScript types model the shape of your data, so you can reason about it at compile time, before the code runs.

🔹 Primitive Types

These represent the basic building blocks of data:

```ts
let x: string = "hello";
let y: number = 42;
let z: boolean = true;
let n: null = null;
let u: undefined = undefined;
```

> These match JavaScript’s typeof values.

🔹 Literal Types

A literal type restricts a value to exactly one option:

```ts
let color: "red"; // only allowed to be "red"
```

🔹 Union Types

A union type means a value can be one of several types:

```ts
let direction: "left" | "right" | "up" | "down";
let id: number | string;
```

> Very useful for modeling flexible APIs and conditional logic.

🔹 Tuple Types

Tuples are fixed-length arrays with known types at each position:

```ts
let point: [number, number] = [3, 4];
let userEntry: [string, number, boolean] = ["Alice", 30, true];
```
