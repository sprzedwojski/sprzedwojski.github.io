---
layout: post
title:  "JS Academy #1: Scope 101"
date:   2018-05-06 00:00:00
cover:	/assets/images/js-academy/mbp-coffee.jpg
disqus: true
categories: javascript
tags: javascript
permalink: /:year/:month/:day/:title/
---

Welcome traveller! The journey to JS-Land begins here. In this episode we will try to make sense of what scope is. You know, the word you hear thrown around here and there, but that you never actually wrapped your head around.

{% include js-academy-box.html %}

### Compiled? Me?

Okay, let's get into it. There is a high probability that you think JavaScript is an interpreted language. WRONG! It's actually dynamic and compiled. But don't beat yourself too hard if you didn't know that, I just learned it recently too. 

The reason we often think it's interpreted is because its compilation takes place just before execution. So it's actually very different from the "traditional" compiled languages, such as C, C++, Java or C#, where compilation and running of the code are separate processes and can happen at different times.

I don't want to get into details as they are not that important for understanding scope, but if you want to dig deeper I found [this interesting thread on StackExchange that you can check out](https://softwareengineering.stackexchange.com/questions/138521/is-javascript-interpreted-by-design){:target="_blank"}.

### Why are you telling me this?

The reason I mentioned compilation is because when JavaScript is processed, it typically undergoes three steps characteristic for compilation:

1. Tokenizing / lexing: dividing a string of words into MEANINGFUL chunks (tokens)
2. Parsing: transforming a stream of tokens into an Abstract Syntax Tree (AST), which is the grammatical representation of the program's structure
3. Code generation: spitting out executable code on the basis of the AST

Let's say we have the following simple program:

```javascript
var niceRoundNumber = 64;
```

In order to be able to run it, a JavaScript "engine" will first compile it, which will result in executable code (depending on the engine it can be some bytecode or pure machine code). <--- REFERENCE NEEDED

### I came here to learn about the scope...

I know, I know! Bear with me, I'm getting there.

So far I mentioned some *engine*, which is the Big Boss that handles the whole execution of our JS program.
Next up we have the *compiler*, which handles all the dirty compiling work.
And finally there is the start of the show, the *scope*.

So what is it exactly? 
> Scope has a look-up list of all the declared variables and a set of rules on how they are accessible to the executing code.

### Two statements

Let's analyze what happens with our program step by step.
First of all we need to realize that `var niceRoundNumber = 64;` are, in fact, two distinct statements.

The *compiler* first looks at `var niceRoundNumber` and knows it has to determine the location of this variable. 
It asks *scope* if variable `niceRoundNumber` already exists for that scope collection. 
If yes, then this statement is ignored.
Otherwise the *compiler* declares new variable `niceRoundNumber` fot that scope collection.

Next the *compiler* looks at `niceRoundNumber = 64` and generates code for this assignment.
When the *engine* later executes this code, it will look the variable up in *scope* and assign the value to it, if found.

===
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
