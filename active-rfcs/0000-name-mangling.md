# Name

- Start Date: 2021-12-05
- RFC PR: [#2](https://github.com/boa-lang/rfcs/pull/2)
- Implementation PR: (leave this empty)
<!-- When when linking to the implementation PR, it should be done in the format of boa-lang/<repo>#<PR number> -->

## Summary

Defines how name mangling will work.

## Basic example

A method of the class `foo` with the signature `method(data: int) -> string` in the module `bar.baz` would be mangled to `boad2m3barm3bazc3fooi6methodp1t3i32r5string`
## Motivation

Most languages "mangle" names of symbols, in order to allow for things like namespacing, overloading, and class/struct methods. This RFC defines how Boa can mangle names

## Detailed design

For purposes of this RFC, "string" refers to a number n followed by n characters.
Additionally, "constant string" is a literal string of characters.

### Function name mangling
A function name will be mangled according to the following scheme
1. Leader: always the constant string `boa`
2. Module: a mangled module name
3. Class (optional): the constant string `c` followed by a string representing the class name
4. Method type (Required if class exists): `i` (for instance methods) or `s` (for static methods)
5. Function name: a string representing the name of the function in Boa code
6. Parameters: the constant string `p` followed by a number n, then n Parameter Descriptors
7. Parameter Descriptors: the constant string `t` followed by a string representing the type name. If the type is a class, the class name is also mangled
8. Return type: the constant string `r` followed by the type name

### Class name mangling:
A class name will be mangled according to the following scheme:
1. Leader: always the constant string `boaclass`
2. Module: a mangled module name
3. Class name: the constant string `n` followed by a string representing the class name

### Module name mangling:
A module name is mangled according to the following scheme
1. Depth: the contstant string `d` followed by the modules "depth" (henceforth referred to as d) in the module tree. `std` has a depth of `1` and `std.math` has a depth of `2`
2. Module names: d repetitions of the following: the constant string `m` followed by a string representing the module name

## Drawbacks

- Generating a mangled name can be slightly costly, and can lead to confusing binaries. A possibility to disable mangling for certain symbols should be considered in the future

## Alternatives

No mangling: this dumps all functions into the same global namespace, and disallows duplicate named functions

## Prior art
Rust: https://rust-lang.github.io/rfcs/2603-rust-symbol-name-mangling-v0.html
https://en.wikipedia.org/wiki/Name_mangling has many other examples
