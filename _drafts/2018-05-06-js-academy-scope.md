---
layout: post
title:  "JS Academy #1: Scope"
date:   2018-05-06 00:00:00
cover:	/assets/images/js-academy/mbp-coffee.jpg
disqus: true
categories: javascript
tags: javascript
permalink: /:year/:month/:day/:title/
---

- JS: general category :dynamic / interpreted, but COMPILED
    - compiled just before execution

- Compilation (traditionally):
    - Tokenizing / lexing: dividing a string of words into MEANINGFUL chunks (tokens)
    - Parsing: stream of tokens --> AST (Abstract Syntax Tree), represents the grammatical structure of the program
    - Code-Generation: AST --> executable (machine) code

- Engine, Compiler, Scope
    - Scope: has a look-up list of all the declared variables and has a set of rules on how they accessible to the executing code
- What happens with `var a = 2;`
    - two distinct statements
    - `var a` --> Compiler checks with Scope if variable `a` already exists for that scope collection. Yes --> statement ignored. No --> new variable `a` declared for that scope collection
        - (this is different for `let`)
    - then Compiler generates code (which Engine will later execute) for the `a = 2` assignment. Engine will look up the variable in Scope and assign to it, if found.
- LHS / RHS lookup
    - LHS: when the variable appears on the left side of an assignment
        - trying to find the variable container, so that it can be assigned
        - "who's the target of the assignment"
        - e.g. `a = 2`
    - RHS: variable on the right side
        - lookup of the value of a variable
        - "who's the source of the assignment"
        - e.g. `console.log(a)`
- Example:
    `function foo(a) {
        console.log(a);
    }

    foo(2);`
    - the `foo(2)` is an RHS lookup --> we need to find the value of `foo`, which should be a function, to be able to execute it
    - when the function is invoked there's an implicit LHS lookup to assign the value `2` to variable `a`

- Nested scopes
    - scopes are nested inside another scopes
    - if a value cannot be found in the immediate scope, the Engine continues the search in the outer scope and so on and so forth, until it reaches the global (outermost) scope

- If a variable has not yet been declared, i.e. is not found in any scope, the LHS and RHS lookups behave differently
    - RHS: `ReferenceError` thrown
    `> console.log(b)
    ReferenceError: b is not defined`
    - LHS: if not in strict mode the global scope will create a new variable in that global scope and hand it back to Engine
    `> c = 3
    3`
        - if in "strict mode" a `ReferenceError` will similarly be thrown
        `> "use strict"; e = 4;
        ReferenceError: e is not defined`
