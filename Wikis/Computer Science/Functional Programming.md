related: [[Object-Oriented Programming]], [[Modular Programming]]
A programming paradigm that strives to create "pure" [[function|functions]].
The goal of functional programming is to minimize any changes from external factors. Creating a straightforward \[f(x,y) return Z] form.

___
# Principles
Functional programming is a paradigm that aims for programs to be a composition of functions rather than a series of commands. The core traits are:
- Declarative programs as opposed to imperative.
- Functions are first-class [[object|objects]]
- Limited [[#Side Effects]]
- [[Mutability|Immutable]] objects
## Ordinal Functions
Functions can have "orders,"
## Purity and Pure Functions
Pure functions are those that have no side effects, whereas impure functions have side effects
### Side Effects
Any result of running a function that is not creating a new return object is considered a side effect. These can include:
- Altering a data frame
- Printing a message
- Writing or pulling from a database
___
# Benefits
Functional programming's primary benefit is repeatability: the outcome will always be a direct result of the input, and no outside factors have an effect on the outcome. It also makes [[parallelization]] (multi-thread processing) much easier
___


#compsci #development #software 