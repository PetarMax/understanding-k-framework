Understanding K Framework Exercises
===================================

Prepared for: [HelloDecentralization 2021](https://hellodecentralization.com/)

Presentation: [Presentation](presentation.pdf)

Setup
-----

-   Install the K Framework: <https://github.com/kframework/k/releases>
-   K Framework documentation: <https://kframework.org>

Building a Language
-------------------

### Exercise 1: Calculator

Use *functional* fragment of K to correctly compute integer arithmetic expressions.
Examples in [tests/calc](tests/calc).

### Exercise 2: Calculator with Boolean Expressions

Remaining in the *functional* fragment of K, extend the calculator to deal with boolean expressions too.
Examples in [tests/calc-bool](tests/calc-bool).

### Exercise 3: Variables in Expressions, Explicit Substitution

Now we must move to the *stateful* fragment of K, which requires adding a *configuration*.
We can hardcode some variable values in the configuration for now, to allow using them in programs.
Examples in [tests/subst](tests/subst).

### Exercise 4.1: Assignment Operator

Updating the entire definition each time to change variable values is impractical.
Instead, we should provide a way for the user to update them instead.
For this, we'll add *statements*, *statement sequencing*, and an *assignment operator*.
Examples in [tests/assignment](tests/assignment).

### Exercise 4.2: Assignment Operator

Now re-do the assignment operator, but using `strict` instead of substitution for expression evaluation.

### Exercise 4.3: Assignment Operator

Now re-do the assignment operator, but using contextual functions instead of substitution for expression evaluation.

### Exercise 5: Control Flow

We want to be able to have *branches* and *loops* in our programs, to do anything interesting.
For that, we'll add an `if` statement, and a `while` loop.
Examples in [tests/control-flow](tests/control-flow).

### Exercise 6: Procedures

We can add procedures to our language to be able to bundle up chunks of code and call them in other expressions.
Examples in [tests/procedures](tests/procedures).

Getting Started With Proofs
---------------------------

In the directory [tests/control-flow](tests/control-flow), there are some specifications which can be proven against the final definition.
You must first kompile with Haskell backend `kompile --backend haskell ...`.
Then you can run proofs using `kprove tests/control-flow/*-spec.k`.
Additionally you can step through the proofs in the debugger using `kprove --debugger tests/control-flow/*-spec.k`.
To make pretty printing of definitions possible, run the command `alias konfig = config | kast --input kore --output pretty /dev/stdin` inside the repl.
