# 📘 JavaScript Keywords — IQ Notes

> **Concept:** What are Keywords in JavaScript?
> **File Used:** `chapter_01_Basics/02_Let concepts.js`

---

## 🔍 What is a Keyword?

A **keyword** is a **reserved word** in JavaScript that has a special, predefined meaning to the JS engine.
You **cannot** use keywords as variable names, function names, or identifiers.

```js
// ❌ Invalid — 'let' is a keyword
let let = 5;  // SyntaxError

// ✅ Valid — 'myLet' is not a keyword
let myLet = 5;
```

---

## 🔍 Concept Breakdown Table

| Category | Keyword | What It Does | Example |
|----------|---------|--------------|---------|
| **Variable Declaration** | `var` | Declares a function-scoped or globally-scoped variable | `var x = 10;` |
| **Variable Declaration** | `let` | Declares a block-scoped variable (reassignable) | `let a = 10;` |
| **Variable Declaration** | `const` | Declares a block-scoped constant (not reassignable) | `const PI = 3.14;` |
| **Control Flow** | `if` | Executes a block if condition is true | `if (a > 5) {}` |
| **Control Flow** | `else` | Executes a block if `if` condition is false | `else {}` |
| **Control Flow** | `else if` | Chains multiple conditions | `else if (a === 5) {}` |
| **Control Flow** | `switch` | Selects one of many code blocks | `switch(a) {}` |
| **Control Flow** | `case` | Defines a branch in `switch` | `case 1:` |
| **Control Flow** | `default` | Fallback in `switch` when no case matches | `default:` |
| **Control Flow** | `break` | Exits a loop or switch | `break;` |
| **Control Flow** | `continue` | Skips current loop iteration | `continue;` |
| **Control Flow** | `return` | Exits a function and optionally returns a value | `return a;` |
| **Loops** | `for` | Loops with init, condition, increment | `for (let i=0; i<5; i++) {}` |
| **Loops** | `while` | Loops while condition is true | `while (a < 5) {}` |
| **Loops** | `do` | Executes block once, then loops while condition is true | `do {} while (a < 5);` |
| **Loops** | `in` | Iterates over object keys | `for (let k in obj) {}` |
| **Loops** | `of` | Iterates over iterable values | `for (let v of arr) {}` |
| **Functions** | `function` | Declares a named function | `function greet() {}` |
| **Functions** | `return` | Returns value from function | `return 42;` |
| **Functions** | `async` | Declares an async function | `async function load() {}` |
| **Functions** | `await` | Waits for a Promise to resolve | `await fetch(url)` |
| **Functions** | `yield` | Pauses a generator function | `yield 1;` |
| **Classes & OOP** | `class` | Declares a class | `class Car {}` |
| **Classes & OOP** | `new` | Creates an instance of a class | `new Car()` |
| **Classes & OOP** | `this` | Refers to the current object | `this.name` |
| **Classes & OOP** | `super` | Calls the parent class constructor/method | `super()` |
| **Classes & OOP** | `extends` | Inherits from a parent class | `class A extends B {}` |
| **Classes & OOP** | `static` | Defines a static method/property | `static getId() {}` |
| **Error Handling** | `try` | Wraps code that may throw an error | `try {}` |
| **Error Handling** | `catch` | Handles the error from `try` | `catch(e) {}` |
| **Error Handling** | `finally` | Always executes after try/catch | `finally {}` |
| **Error Handling** | `throw` | Manually throws an error | `throw new Error("fail")` |
| **Modules** | `import` | Imports bindings from a module | `import fs from 'fs'` |
| **Modules** | `export` | Exports bindings from a module | `export default fn` |
| **Type Checks** | `typeof` | Returns type of a value as a string | `typeof a` → `"number"` |
| **Type Checks** | `instanceof` | Checks if object is instance of a class | `a instanceof Array` |
| **Type Checks** | `void` | Evaluates expression and returns `undefined` | `void 0` |
| **Boolean/Logic** | `true` | Boolean true literal | `let flag = true;` |
| **Boolean/Logic** | `false` | Boolean false literal | `let flag = false;` |
| **Null/Undefined** | `null` | Intentional absence of value | `let x = null;` |
| **Null/Undefined** | `undefined` | Variable declared but not assigned | `let y; // undefined` |
| **Deletion** | `delete` | Removes a property from an object | `delete obj.name` |
| **Strict Mode** | `debugger` | Triggers a breakpoint in DevTools | `debugger;` |
| **Strict Mode** | `with` | Extends scope chain (deprecated) | `with(obj) {}` |

---

## 🧪 Example Walkthrough — `02_Let concepts.js`

```js
let a = 10;
console.log(a);
```

| Token | Is it a Keyword? | Type | Role |
|-------|-----------------|------|------|
| `let` | ✅ Yes | Variable Declaration Keyword | Declares block-scoped variable `a` |
| `a` | ❌ No | Identifier | Variable name |
| `=` | ❌ No | Operator | Assignment |
| `10` | ❌ No | Literal | Numeric value |
| `console` | ❌ No | Built-in Object | Global console object |
| `.log` | ❌ No | Method | Outputs to console |

---

## 🔁 Pipeline Diagram

```
┌─────────────────────────────────────┐
│         JavaScript Source Code      │
│     let a = 10;                     │
│     console.log(a);                 │
└──────────────┬──────────────────────┘
               │
       [ Lexer / Tokenizer ]
               │
               ▼
┌─────────────────────────────────────┐
│            Token Stream             │
│  KEYWORD(let) | ID(a) | OP(=)      │
│  NUM(10) | PUNC(;) | ...           │
└──────────────┬──────────────────────┘
               │
       [ Parser → AST ]
               │
               ▼
┌─────────────────────────────────────┐
│         Abstract Syntax Tree        │
│  VariableDeclaration                │
│    └── kind: "let"  ← KEYWORD      │
│    └── id: "a"      ← Identifier   │
│    └── init: 10     ← Literal      │
└──────────────┬──────────────────────┘
               │
       [ V8 Executes ]
               │
               ▼
        ✅  Output: 10
```

---

## ⚡ TL;DR

| Question | Answer |
|----------|--------|
| What is a **keyword**? | A reserved word with special meaning in JS — cannot be used as an identifier |
| How many keywords does JS have? | ~50 keywords (+ reserved words for future use) |
| Which keyword is in `02_Let concepts.js`? | `let` — declares a block-scoped variable |
| Difference: `var` vs `let` vs `const`? | `var` = function-scoped; `let` = block-scoped, reassignable; `const` = block-scoped, not reassignable |
| Are `true`, `false`, `null` keywords? | Yes — they are **literal keywords** (reserved values) |
| Can keywords be variable names? | ❌ No — causes `SyntaxError` |

---

*Generated by GitHub Copilot | IQ Notes Series*
