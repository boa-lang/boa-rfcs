# Name

- Start Date: 2021 8 8
- RFC PR: [#0](https://github.com/boa-lang/rfcs/pull/0) 
- Implementation PR: (leave this empty)
<!-- When when linking to the implementation PR, it should be done in the format of boa-lang/<repo>#<PR number> -->

## Summary

This RFC is a proposition of what the boa syntax could and may look like.
It use ideas and concepts discussed and invented in the boa discord.

Boa is a, Statically Typed/Object Oriented Programming, compiled general purpose programming language infrastructure resembling python.

The goal of Boa is to provide a similar development workflow to python, while also allowing the developer to create, fast and complex apps.

## Basic example

```py
# Hello world program

def main():
    print("Hello world")
```

```py
# Greetings program

def greet(name: string): string:
    return f'Hello {name}!'

def main():
    print(greet("Tobias"))
    print(greet(10)) # Error: Expected type of string, Got number at greet.py:8
```

## Motivation

Why should we do this? What use cases will it support? What is the expected outcome?

This is an attempt at seeing what are the flaws and benefits of such syntaxes.
It is also made to help see what's best for boa and it's future

## Detailed design

### Lambdas

In vanilla python, lambdas look something like this.

(Reference)[https://www.w3schools.com/python/python_lambda.asp]

```py
lambda arguments : expression
```

As discussed in discord, something more like js is not only more elegant, but also way more readable.

```py
#All options

(arguments) => expression
argument => expression
() => expression

(arguments): function_body
argument: function_body
(): function_body
```

## Alternatives

What other solutions have been considered? Why this solution rather than them? What is the impact of not doing this?

## Prior art

Has anyone else done this before? How did it work out for them? Do any articles exist that discuss this?

Note that precedent alone does not motivate an RFC. We may sometimes diverge from common practices.

Only include this section if applicable.

## Unresolved questions

Syntaxes and ambiguous cases that might not have been discussed or worked on yet