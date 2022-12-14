# JavaScript Coding Guide

Assumptions

- Relatively little code; runs client-side, that is, in the browser.
- Mostly a one-man show, so collaboration is not an issue.
- The JavaScript code is sent directly; no minification or obfuscation.

General

- Keep lines of code to 80 characters at most.
- Indent with 2 spaces. Do not use tab characters.
- Use `\n` as the line terminator; do not use `\r` or `\r\n`.
- Use blank lines to separate the code into "paragraphs".
- Prefer English for all comments and identifiers.
- Avoid non-ASCII characters in comments and identifiers.
- Terseness is acceptable (obfuscation is not).

Comments

- Outdated comments are worse than no comments.
- Comments use proper spelling and grammar.
- Use line comments to explain what is not obvious.
- Use block comments to document functions (and during
  development to temporarily disable a block of code).

Naming

- Avoid non-ASCII characters.
- Do not use `$` or `\` in names.
- Do not use `_` as the first or last character of a name.
- Begin most variable and function names with a lower-case letter.
- Constructor functions to be used with the new operator
  should start with a capital letter.
- Global variables in browsers should be in all caps.

Functions

- The name of a function reflects its purpose.
- For all non-trivial functions, have a header (block) comment
  describe the purpose and use of the function.
- Enclose all sub blocks in `{` and `}`.
- Wrap immediately invoked function expressions (IIFE) in parens
  to make clear that the value produced is the function result,
  not the function: var foo = (function(){...}())

Variables

- Declare all variables before use, at the beginning of their scope
  (for var that means at the top of the function).
- The name of a variable reflects its use.
- Use conventional short names for loop counters (e.g. `i`, `j`).
- A comment defines purpose and use of widely scoped variables.
- Use let and const if targeting recent browsers; beware that
  let and const are an ES6 feature, introduced only in 2015.

Modularity

- use the module pattern (or a module system)

Miscellaneous

- Place at most one statement on a line.
- Put a `;` at the end of every simple statement.
- Use [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode):
  say `"use strict";` at the beginning of the module (available since ES5
  in 2009; beware of possible concatenation problems with strict mode).
- Use the strict equality operators `===` and `!==` operators.
  The `==` and `!=` operators do type coercion and should be avoided.
- Prefer `{}` over `new Object()` and `[]` over `new Array()`.
- Put the return value expression on the same line as the return
  keyword (to avoid semicolon insertion).
- Do not use expressions as statements, except: assignments,
  invocatoins, and delete (JS allows any expr as a stmt).
- Avoid assignments in the condition part of if and while statements.
- Do not use the `with` statement.
- Avoid `eval` and its aliases, the `Function` constructor and
  string arguments to `setTimeout` and `setInterval`.

Spacing besides indentation is somewhat irrelevant;
here I prefer a terse style as no minification is used.

Style checkers are always opinionated and therefore a pain; don't
use them. Linting, on the other hand, can be a valuable dev aid.
Prefer semicolons, or be sure to understand JavaScript's automatic
semicolon insertion rules.

References:
[Crockford](http://crockford.com/javascript/code.html),
[Fossil](https://www.fossil-scm.org/index.html/doc/trunk/www/style.wiki),
[Bevacqua](https://github.com/bevacqua/js)


    # editorconfig.org
    root = true
    [*]
    charset = utf-8
    end_of_line = lf
    [*.js]
    indent_style = space
    indent_size = 2
    trim_trailing_whitespace = true
    insert_final_newline = true
    [*.md]
    trim_trailing_whitespace = false


Beyond Style

- Avoid console output in production.
- Don't declare functions inside loops (modified closure problem).
- Optimize for performance only if there's a measurable problem.  
  Or: “premature optimization is the root of all evil” (Knuth).
- Hoisting example: the following code logs two times "undefined".
  Be sure to understand why.


```JavaScript
var value = 42;
test();
function test(){
  console.log(typeof value);
  console.log(value);
  var value = 99;
}
```
