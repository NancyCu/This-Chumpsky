# Chumpsky in Your Browser

This mini web app lets you convert any context‑free grammar (CFG) to Chomsky
Normal Form (CNF) directly in your browser. It runs entirely offline using
[Pyodide](https://pyodide.org/), so there is nothing to install.

## Getting Started

1. **Clone or download** this repository.
2. **Open `index.html`** in any modern web browser.
3. A page titled *"Con. Free Grammar → Chomsky Normal Form"* will appear.

Paste your grammar and optionally jot down a short description of the
language it generates. Hit **Convert to CNF**, and the page will display the
transformed grammar along with each conversion stage. You can also click
**Generate Words** to produce a few sample words from your grammar.

## Example Grammar

Enter each production on a separate line using `->` (or `→`) and separate
alternatives with `|`. You can write the empty string as `ε` or `E`.

```text
S -> AB | a
A -> aA | ε
B -> b
```

## What You'll See

After pressing **Convert to CNF**, the page walks through all the steps of the
conversion. The *Show Steps* tab lists them in order, similar to:

1. **Add a new start symbol**
2. **Remove ε‑productions**
3. **Remove unit productions**
4. **Remove useless symbols**
5. **Final CNF form**

Colored output makes variables and terminals easy to spot, giving the process a
bit more flair.

That's it! Enjoy experimenting with grammars and exploring how they transform
into Chomsky Normal Form.

## Regular Expression Examples

Although the app focuses on context‑free grammars, some simple grammars describe languages that can also be written using regular expressions. Here are a few examples:

- A grammar with productions:

  ```text
  S → aB
  B → bB | ε
  ```

  generates the language `ab*`.

- The grammar

  ```text
  S → aS | bS | ε
  ```

  corresponds to the expression `(a ∪ b)*`.

- If Σ is your alphabet and you want all non‑empty strings ending in `b`, a concise regex is `Σ+b`.

These representations can be handy when comparing a CFG to a simpler pattern.
