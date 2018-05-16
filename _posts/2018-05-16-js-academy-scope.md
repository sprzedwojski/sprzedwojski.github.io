---
layout: post
title:  "JS Academy #1: Scope 101"
date:   2018-05-16 00:00:00
cover:	/assets/images/js-academy/mbp-coffee.jpg
disqus: true
categories: javascript
tags: javascript
permalink: /:year/:month/:day/:title/
---

Welcome traveller! The journey to JS-Land begins here. In this episode we will try to make sense of what scope is. You know, the word you hear thrown around here and there, but that you never actually wrapped your head around.

{% include js-academy-box.html %}

### Compiled? Me?

Okay, let's get into it. There is a high probability that you think JavaScript is an interpreted language. WRONG! It's actually compiled! 
<!-- But don't beat yourself too hard if you didn't know that, I just learned it recently too.  -->

The reason we often think it's interpreted is because its compilation takes place just before execution. So it's actually very different from the "traditional" compiled languages, such as C, C++, Java or C#, where compilation and running of the code are separate processes and can happen at different times.

I don't want to get into details as they are not that important for understanding scope, but if you want to dig deeper I found [this interesting thread on StackExchange that you can check out](https://softwareengineering.stackexchange.com/questions/138521/is-javascript-interpreted-by-design){:target="_blank"}.

### Why are you telling me this?

The reason I'm mentioning compilation is because scope is involved in this process, which consists of 3 steps:
<!-- when JavaScript is processed, it typically undergoes three steps characteristic for compilation: -->

1. Tokenizing / lexing: dividing a string of words into meaningful chunks (tokens)
2. Parsing: transforming a stream of tokens into an Abstract Syntax Tree (AST), which is the grammatical representation of the program's structure
3. Code generation: spitting out executable code on the basis of the AST

Let's say we have the following simple program:

```javascript
var niceRoundNumber = 64;
```

In order to be able to run it, a JavaScript "engine" will first compile it, which will result in executable code. 
<!-- (depending on the engine it can be some bytecode or pure machine code). <--- REFERENCE NEEDED -->

### I came here to learn about the scope...

I know, I know! Bear with me, I'm getting there.

So far I mentioned *engine*, which is the Big Boss that handles the whole execution of our JS program.
Next up we have the *compiler*, which handles all the dirty compiling work.
And finally there is the star of the show, the *scope*.

So what does it do exactly? 
> Scope has a look-up list of all the declared variables and a set of rules on how they are accessible to the executing code.

### Two statements

Let's analyze what happens with our program step by step.
First of all we need to realize that `var niceRoundNumber = 64;` are, in fact, two distinct statements.

The *compiler* first looks at `var niceRoundNumber` and knows it has to determine the location of this variable. 
It asks *scope* if variable `niceRoundNumber` already exists for that scope collection. 
If yes, then this statement is ignored.
Otherwise the *compiler* declares new variable `niceRoundNumber` fot that scope collection.

Next the *compiler* looks at `niceRoundNumber = 64` and generates code for this assignment.
When *engine* later executes this code, it will look the variable up in *scope* and assign the value to it, if found.

### LHS / RHS lookup

In fact there are 2 kinds of scope lookups: left-hand side (LHS) and right-hand side (RHS).
With a dose of simplification we can say that LHS happens when the variable appears on the left side of an assignment, and RHS when... you guessed it, when it's on the right side.

In LHS the idea is: *we need to find the container of the variable, to assign it a new value.*
It cares about __who is the target of the assignment__.
Example of LHS: `myVar = 2`

In RHS we are trying to *lookup the value of a variable*.
We care about __who is the source of the assignment__.
Example of RHS: `console.log(myVar)`

### Nested scopes

The thing about scopes is they can be nested. Just like birds. Well, maybe not, but still...
Nested scopes are scopes inside scopes. Like in that movie "Inception", you know? 
Okay, enough with the comparisons...

Anyway, what you need to know is that if a value cannot be found in the immediate scope, the *engine* will continue searching in the outer scope and so on and so forth, until it reaches the global (outermost) scope.

And this brings us to...

### Not everyone can handle an undeclared variable

If a variable has not yet been declared, i.e. is not found in any scope, the LHS and RHS lookups behave differently:

* RHS - a `ReferenceError` is thrown:
```javascript
> console.log(b)
ReferenceError: b is not defined
```
* LHS - if not in strict mode the global scope will create a new variable in that global scope and hand it back to *engine*:
```javascript
> c = 3
3
```

One caveat is that if we are in ["strict mode"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions_and_function_scope/Strict_mode){:target="_blank"} (more on that in future articles) a `ReferenceError` will similarly be thrown in the case of LHS:
```javascript
> "use strict"; e = 4;
ReferenceError: e is not defined
```

### In the next episode

Thanks for reading and come back next week! We'll talk about lexical scope ;)

{% include js-academy-box-disclaimer.html %}
