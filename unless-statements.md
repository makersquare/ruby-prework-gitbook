# `unless` Statements

We know that `if` expressions check to see if a given conditional evaluates to `true`. `unless` does the opposite: it checks that the conditional evaluates to `false`.

```ruby
x = 5
unless x > 3
  puts "x is less than 3"
end
```

What we are saying in this code is `puts "x is less than 3"` *unless* `x` is greater than 3. Because `x` is 5 nothing will be printed to the screen. You can also include an `else` statement just like with `if`, however, it should be noted that using `unless` with an `else` is generally considered bad form. Any such conditional expression can and should be refactored to use `if`/`else` instead.

#### `unless` modifier

Like `if`, `unless` can also be used as a modifier. The syntax is identical:

```ruby
x = 6
puts "x is greater than 5" unless x < 5
```

`unless` is frequently used this way at the very beginning of a method to raise exceptions based on some condition. This is considered good style. It allows you to clearly and concisely control the flow of a method before serious code is evaluated.
