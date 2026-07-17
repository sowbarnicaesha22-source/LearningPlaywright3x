# 📘 JavaScript Identifier Rules — IQ Notes

> **Concept:** What are Identifiers and what rules govern them in JavaScript?
> **Related File:** `03-Chapter Identifier/`

---

## 🔍 What is an Identifier?

An **identifier** is a **name** given to a variable, function, class, parameter, label, or object property in JavaScript.

```js
let userName = "Sowbarnica";   // 'userName' is an identifier
function greetUser() {}        // 'greetUser' is an identifier
const MAX_LIMIT = 100;         // 'MAX_LIMIT' is an identifier
```

---

## 🔍 Identifier Rules — Breakdown Table

| # | Rule | ✅ Valid Example | ❌ Invalid Example | Why Invalid? |
|---|------|-----------------|-------------------|--------------|
| 1 | Must **start with a letter**, `_` (underscore), or `$` (dollar sign) | `name`, `_name`, `$name` | `1name`, `@name` | Cannot start with a digit or special char |
| 2 | Can contain **letters, digits, `_`, `$`** after the first character | `user1`, `my_var`, `$val2` | `my-var`, `my var` | Hyphens and spaces not allowed |
| 3 | **Cannot be a reserved keyword** | `myLet`, `returnValue` | `let`, `return`, `class` | Keywords are reserved by JS engine |
| 4 | **Case-sensitive** — uppercase and lowercase are different | `name` ≠ `Name` ≠ `NAME` | — | All three are distinct identifiers |
| 5 | **No spaces** allowed inside an identifier | `firstName` | `first Name` | Space splits it into two tokens |
| 6 | **No special characters** except `_` and `$` | `_id`, `$price` | `my@var`, `val#1` | Special chars are not permitted |
| 7 | **No length limit** (but keep it readable) | `userAccountLoginName` | — | Technically unlimited, but avoid very long names |
| 8 | **Unicode letters** are allowed (ES5+) | `café`, `résumé` | — | Valid but not recommended for cross-team readability |

---

## 🧪 Example Walkthrough

```js
let userName = "Sowbarnica";   // ✅ starts with letter, camelCase
let _count = 0;                // ✅ starts with underscore
let $price = 99.99;            // ✅ starts with dollar sign
let user1 = "Admin";           // ✅ digit after first char is fine

let 1user = "Bad";             // ❌ starts with digit
let my-var = 10;               // ❌ hyphen not allowed
let let = 5;                   // ❌ 'let' is a reserved keyword
let my var = 20;               // ❌ space inside identifier
```

| Identifier | Valid? | Reason |
|-----------|--------|--------|
| `userName` | ✅ | Starts with letter, camelCase |
| `_count` | ✅ | Starts with `_` |
| `$price` | ✅ | Starts with `$` |
| `user1` | ✅ | Digit used after first char |
| `1user` | ❌ | Cannot start with a digit |
| `my-var` | ❌ | Hyphen `-` is not allowed |
| `let` | ❌ | Reserved keyword |
| `my var` | ❌ | Space inside identifier |
| `UserName` | ✅ | Different from `userName` (case-sensitive) |

---

## 📐 Naming Conventions (Best Practices)

| Convention | Style | Used For | Example |
|-----------|-------|----------|---------|
| **camelCase** | first word lowercase, rest Title | Variables, Functions | `userName`, `getUserData()` |
| **PascalCase** | Every word starts uppercase | Classes, Constructors | `UserAccount`, `TestRunner` |
| **UPPER_SNAKE_CASE** | All caps with underscores | Constants | `MAX_RETRIES`, `BASE_URL` |
| **_underscorePrefix** | Leading underscore | Private/internal convention | `_internalState` |
| **$dollarPrefix** | Leading dollar sign | jQuery / framework-generated | `$element` |

---

## 🔁 Pipeline Diagram

```
┌──────────────────────────────────────────┐
│           JavaScript Source Code         │
│   let userName = "Sowbarnica";           │
└──────────────────┬───────────────────────┘
                   │
          [ Lexer / Tokenizer ]
                   │
                   ▼
┌──────────────────────────────────────────┐
│              Token Stream                │
│  KEYWORD(let) | IDENTIFIER(userName)    │
│  OP(=) | STRING("Sowbarnica") | PUNC(;) │
└──────────────────┬───────────────────────┘
                   │
      [ Identifier Validation Rules ]
                   │
     ┌─────────────┴──────────────┐
     │                            │
  PASS ✅                      FAIL ❌
  (valid name)              (SyntaxError)
     │
     ▼
[ Parser builds AST ]
     │
     ▼
[ V8 Engine executes ]
     │
     ▼
  ✅ Variable 'userName' = "Sowbarnica"
```

---

## ⚡ TL;DR

| Question | Answer |
|----------|--------|
| What is an **identifier**? | A name for a variable, function, class, or parameter |
| Can it start with a number? | ❌ No — must start with a letter, `_`, or `$` |
| Are identifiers **case-sensitive**? | ✅ Yes — `name`, `Name`, `NAME` are three different identifiers |
| Can you use a keyword as an identifier? | ❌ No — causes `SyntaxError` |
| What characters are allowed? | Letters, digits (not first), `_`, `$` |
| Best naming style for variables? | `camelCase` |
| Best naming style for classes? | `PascalCase` |
| Best naming style for constants? | `UPPER_SNAKE_CASE` |

---

*Generated by GitHub Copilot | IQ Notes Series*
