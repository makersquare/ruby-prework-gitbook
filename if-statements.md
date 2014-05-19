# `if` Statements

Frequently when writing code you need to determine if you should do something based on some condition within your program. `if` is Ruby's basic conditional statement constructor. It takes one argument which uses one or more of the standard comparison operators (`==, !=, <, >, <=, >=`). If the argument evaluates to true it executes the code on that branch. Lets take a look at some examples.

```ruby
num = 6

# Example 1
if num < 10
  puts "num is less than 10."
end

# Example 2
if num == 6
  puts "num is 6!"
end

# Example 3
if num < 10 && num != 5
  puts "num is less than 10 but not equal to 5"
end
```

In all three examples the conditionals evaluate to `true`. The first two are pretty self explanatory. In Example 1, if num is less than 10 `"num is less than 10"` will be printed to the screen; in example 2, `"num is 6"` will be printed to the screen. Example 3 may seem a little odd at first. The `&&` operator requires the conditionals on either side of it to evaluate to true in order for the code on that branch to be evaluated. Because `num` is less than 10 _**and** _ not equal to 5 `"num is less than 10 but not equal to 5"` will be printed.



If you type this out in IRB the string `"num is greater than 10"` will be printed to your screen. If you made `num` smaller than 10 nothing would be printed. If you'd like to print something if `num` is smaller than 10 you can use `else`.

```ruby
num = 5

if num < 10
  puts "num is less than 10"
else
  puts "num is greater than 10"
end
```

Sometimes this "either-or" format isn't precise enough. You may want to check for multiple conditions. That's where `elsif` comes in handy.

```ruby
num = 5

if num < 10
  puts "num is less than 10"
elsif num > 0
  puts "num is greater than 0"
else
  puts "num is less than 0"
end
```

Here our code first checks to see if `num` is greater than 10, it is not so our program checks to see if `num` is greater than 0. It is and so `"num is greater than 0"` is printed to the screen.

Question:

Is it possible to ever have `"num is less than 0"` printed to the screen? Why or why not?

#### `if` modifier

`if` can also be used as an expression modifier. To many, modifiers are of dubious value considering the ease with which they can be abused. Here we'll learn what a modifier is and when it would be appropriate to use one. Let's have a look at a basic use of the `if` modifier.

```ruby
def divide_nums(x, y)
  return "Divide by 0!!!" if y.zero?
  x / y
end

divide_nums(9, 0)  #=> "Divide by 0!!!"
divide_nums(9, 3)  #=> 3
```

In the above method, `divide_nums`, we take two numbers and divide the first one by the second. At the beginning of the method we say that the method should return `"Divide by 0!!!"` if `y` is equal to 0. The first time we call the method our message is returned because dividing by zero is an illegal operation. The second time we call the method we provide two valid integers and `x / y` is evaluated and returned.
