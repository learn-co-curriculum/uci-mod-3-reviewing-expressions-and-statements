# Reviewing Expressions and Statements

## Learning Goals

- Define expressions
- Define statements
- Review selection statements
- Review repetition statements

## Introduction

In the upcoming lessons, we are going to review the core concepts of procedural
Ruby. The first things to review are expressions and statements.

## Define Expressions

An [expression][] is the combination of one or more constants, variables, and
operators, interpreted together to produce a value.

Expressions are the basic piece of communication between you and Ruby. With
expressions, we _say_ something to Ruby, and Ruby will _always respond_. When
we write:

```ruby
5 + 10
```

Ruby will respond with:

```ruby
 => 15
```

In this case, we've provided constants (`5` and `10`) and an operator (`+`),
Ruby has interpreted their combination as the addition of two `Integer`s and
returned the value `15`.

> **ASIDE**: Constant, in this case, is referring to a **value** that never
> changes. The numbers `5` and `10` will never be anything but `5` and `10`.

Expressions also handle two critically important things in programming: variable
assignment and look up.

```Ruby
good_dog = 'Zara'
```

With one expression, we are able to assign value to a variable. In the example
above, the value `Zara` is being assigned to the variable `good_dog`. With a
second expression, we can look up that variable:

```ruby
good_dog
#=> 'Zara'
```

Variables store values so we can use them later on.

```Ruby
first_number = 5
second_number = 10

first_number + second_number
```

```ruby
 => 15
```

If we were to change out the values for `first_number` and `second_number`, we
can keep our third expression the same but get different results.

```Ruby
first_number = 100
second_number = 100

first_number + second_number
```

```ruby
 => 200
```

Writing one expression, `5 + 10`, we have the answer to _one_ math question.
With just _three_ expressions in a row, we have built an _adding machine_.

## Define Statement

In programming, [statements][] carry out an _action_. Unlike expressions,
statements usually do not return anything. Some statements are used to carry out
an action such as printing something to the command line. If the following was
run in IRB:

```text
2.6.1 :001 > puts "hello"
```

It would return:

```text
hello
 => nil
```

The statement, `puts "hello"`, will cause Ruby to output the string `"hello"`.
It _does not return the string_. It returns `nil`.

Normally in Ruby, the code is read from left to right, top to bottom. This is
the **default sequence**. Statements, however, can cause deviations in this
sequence by either **selection** or **repetition**.

### Selection Statements

Selection statements disrupt the "default sequence" by asking Ruby to run a
test, decide whether to follow the path and then move back to the default
sequence.

```ruby
raining = true

if raining
  puts "Bring an umbrella!"
else
  puts "Have a nice day!"
end
```

Above is an example of an [`if..else..end`][] statement containing two separate
`puts` statements (three separated statements in total). Run in IRB, it will
print:

```text
Bring an umbrella!
 => nil
```

Switch `raining` to `false` and run it again:

```text
Have a nice day!
 => nil
```

Although there are two `puts` statements inside the `if..else..end` statement,
only one will run, depending on the value of `raining`.

### Repetition Statements

Repetition statements let us disrupt default flow by repeating. The `while`
method for instance, means "do something while `<value>` is true" That
"something" is held inside a `do...end` block:

```ruby
count = 0

while count < 5 do
  puts count
  count += 1
end
```

> **Reminder**: The `+=` is the same as saying 'take this thing, count, and assign it to whatever it was, plus 1'

In IRB, the result is that `puts` is called five times:

```text
0
1
2
3
4
 => nil
```

Each time, `count` is a different value, as it is being incremented by one every
time the `while` loop executes.

## Conclusion

Expressions and statements make up the core building blocks of Ruby code.

Expressions allow us to converse with Ruby, as they always return a value. We
can use them for things like to evaluating operations and assigning and looking
up variables.

Statements are for carrying out actions. They can modify the default sequence.
Statements can cause Ruby to ignore lines of code or choose some over others,
_if_ a statement's condition is not met. They can also cause lines of code to
repeat as many times as we'd like.

## Resources

- [If Statements][if]
- [While Loops][while]

[expression]: https://en.wikipedia.org/wiki/Expression_(computer_science)
[statements]: https://en.wikipedia.org/wiki/Statement_(computer_science)
[if]: https://ruby-doc.org/core-2.2.0/doc/syntax/control_expressions_rdoc.html#label-if+Expression
[while]: https://ruby-doc.org/core-2.2.0/doc/syntax/control_expressions_rdoc.html#label-while+Loop
