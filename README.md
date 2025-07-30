# typescript-notes

## Menu

- [The Backstory](#the-backstory)

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
