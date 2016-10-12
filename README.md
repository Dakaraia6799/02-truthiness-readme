# Truthiness

## Overview

In this lesson, we'll explain the significance of truthiness in programming and identify boolean values in Ruby. 

## Objectives

1. Define control flow and how Boolean values help in implementing it in programming.
2. List what is truthy and falsey in Ruby.
3. Use the double bang operator to determine truthiness in Ruby. 
4. Review the concept of boolean values.
5. Use boolean operators and identify their return values.
6. Use comparison operators and identify their return values.

## Introduction

![Truthiness](http://upload.wikimedia.org/wikipedia/en/thumb/8/85/Truthiness.png/300px-Truthiness.png)

Many programming languages, including Ruby, have native boolean (true or false) data types. In Ruby they're expressed directly as `true` and `false`.

**Advanced:** *This is not the case in all languages. In Python, boolean values are capitalized,* `True` *and* `False`, *while in Objective-C they are different words* `YES` *and* `NO`. *However, they all represent the same concept of Boolean logic.*

These boolean values come in handy in programming when we want to implement control flow. Control flow is the idea that we can tell our program to execute certain lines of code based upon certain conditions.

### Booleans and Flow Control

For example, *if* I am tired, then I will take a nap. Otherwise, I will keep reading this insightful and informative readme. You could also invert the perspective like in this example:

If it is *true* that I am tired, then I will take a nap. If it is *false* that I am tired, then I won't take a nap.

Flow control is predicated on these true-or-false boolean values. The adjectives "truthy" and "falsey" are a programming convention for describing the *state* of being true and the *state* of being false.

What this example amounts to is this: we want to be able to use non-boolean values (like strings or integers) in a boolean context; we want to be able to say, "*if* a certain statement *evaluates* to true (or is "truthy"), then execute these certain lines of code."

Consequently, Ruby must have a way of determining what counts as true at a given moment—or what is "truthy" versus what is "falsey".

Remember, don't worry about understanding control flow and implementing it right now. This is just to provide some background about why we care about the concept of truthiness in Ruby.

## What Is 'truthy' and 'falsey' in Ruby?

Programming languages are software, too! That means the people who built Ruby had to decide what is truthy and what is falsey. Different languages make different decisions.

**In Ruby only false and nil are falsey. Everything else is truthy (yes, even 0 is truthy).**

Become familiar with the following chart:

| Value        | Truthy? |
|:------------:|:-------:|
|0             | yes     |
| " "          | yes
|"hello"       | yes     |
|nil           | no      |
|6.7           | yes     |
|true          | yes     |
|false         | no      |
|[1,2]         | yes     |
|{:hi=>"there"}| yes     |

You get the idea!

**Top-Tip:** Even an empty string, `" "`, is truthy! This might seem kind of strange, but it will make more sense once we learn more about object orientation. For now, keep in mind that even an empty string is an instance of the String class. Again, that sentence might not mean a lot to you right now, but it will soon...


## Booleans

We've already learned a bit about the boolean (true-or-false) data type. In Ruby, a boolean refers to a value of either `true` or `false`, both of which are defined as their very own data types. Every appearance, or instance, of `true` in a Ruby program is an instance of `TrueClass`, while every appearance of `false` is an instance of `FalseClass`.

For now, we don't need to understand the concept of classes in depth. Just know that classes serve as templates for Ruby objects. Think of `TrueClass` and `FalseClass` like cookie cutters––there is a `TrueClass` cookie cutter and a `FalseClass` cookie cutter and every appearance of `true` or `false` is like a cookie made with its respective cookie cutter.

## Boolean Operators

How do we create boolean values in a Ruby program? Well, you can actually type `true` or `false` *or* we can write statements that *return* `true` or `false`. Now that we understand the concept of "truthiness"—that certain types of data are "truthy" and certain others are "falsey"—we can understand how to write such statements.

Let's learn how to use **boolean operators** to write statements that return `true` or `false`.

### What are Boolean Operators?

Boolean operators are really methods which means that they have return values. What do they return? `true` or `false` of course!

In Ruby there are three main boolean operators:

* `!` ("single-bang") which represents "NOT",
* `&&` ("double-ampersand") which represents "AND", and
* `||` ("double-pipe") which represents "OR".

For an `&&` ("and") to evaluate to `true`, both values of either side of the symbol must evaluate to `true`. For example:

```ruby
true && true #=> true

true && false #=> false
```

For an `||` ("or") to evaluate to `true`, only one value on either side of the symbol must evaluate to `true`. For example:

```ruby
false || true #=> true
```

Finally, a `!` ("not") reverses the logical state of its operand: if a condition is `true`, then `!` will make it `false`; if it is `false`, then `!` will make it `true`. For example:

```ruby
!true #=> false

!false #=> true
```

## Comparison Operators

To check if two values are equal, we use the *comparison operator* represented with `==` ("double-equal-sign"). If two values are equal, then the statement will return `true`. If they are not equal, then it will return `false`. For example:

```ruby
1 == 1 #=> true

1 == 7 #=> false
```

**Top-tip:** *The comparison operator* `==` *is distinct from the assignment operator* `=` *that is used to set a variable equal to a value. Mistaking these for each other is a common cause of unexpected behavior.*


## More Comparison Operators

Ruby is good at comparing things. For instance, it knows that `14` is larger than `3`. Let's see that in action.

```rb
14 > 3 #=> true
```

Here, `14` is larger than `3`, so Ruby evaluates this to `true`. Comparisons in Ruby always evaluate to `true` or `false`.

The commonly used comparison operators are:

| Operator | Operation |
|:--------:|:----------|
| `==`     | If the values of the two operands are *equal*, then the evaluation is `true`. |
| `!=`     | If the values of the two operands are *not equal*, then the evaluation is `true`. An easy way to read this is, "Is the left DIFFERENT from the right?"  If the values are different, the comparison returns `true`.|
| `>`      | If the value of the left operand is *greater than* the value of the right operand, then the evaluation is `true`. |
| `<`      | If the value of the left operand is less than the value of the right operand, then the evaluation is `true`. |
| `>=`     | If the value of the left operand is *greater than or equal to* the value of the right operand, then the evaluation is `true`. |
| `<=`     | If the left operand is *less than or equal to* the value of the right operand, then the evaluation is `true`. |

Ruby can compare a lot more than just numbers. It can also compare strings:

```rb
"yellow" == "yellow" #=>true
```

And variables with known values:

```rb
my_mood = "happy"

my_mood == "happy" #=> true
```

It can also compare variables against other variables:

```ruby
easter_eggs = 16
ducklings = 3

easter_eggs > ducklings #=> true

ducklings >= easter_eggs #=> false

ducklings == easter_eggs #=> false

# if you call class on a variable, you can see if it's a string, an integer, etc.

ducklings.class #=> Fixnum
easter_eggs.class #=> Fixnum
ducklings.class == easter_eggs.class #=> true
```

Comparison operators are essential to developing logical flow.

## Quiz

Let's see if you've really gotten the hang of this.  Test out your knowledge of **truthiness** with some questions:  
[bmuellerhstat.github.io/ruby-truthiness-quiz/](https://bmuellerhstat.github.io/ruby-truthiness-quiz/)