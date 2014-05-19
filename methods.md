# Methods

Methods are bits of instructions that are saved to a name that can be called later. We use the keyword `def` to tell the interpreter that we are creating a new method and the keyword `end` to say that that is the end of the method. The word following def is the name of the method. Here's an example.

```ruby
def five_plus_two
  puts 7
end
```

When you call `five_plus_two` the number 7 will be printed to the screen. This method will always print that one string. You can write a method that expects to be called with some arguments too. If you wanted to add any two numbers together and print the result to the screen you could write a method like this:

```ruby
def add_numbers(num1, num2)
  puts num1 + num2
end
```

Here, `add_numbers` is the name of the method. Everything between the parentheses are called parameters. Parameters are separated by commas and can be called just about anything; it's best to call them something that is related to what you expect them to be.
