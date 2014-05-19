# `case` Expressions

In most languages case (or switch as they are often known) expressions take a value and check for equality against several constants and then executes some code if a match is found. Case expressions in Ruby work similarly but because it uses something called the "case-equality" operator (`===`) to do comparison it is a bit more flexible. Let's have a look at a very simple example.

```ruby
grade = gets.chomp
case grade
when 'A'
  puts "Great job!"
when 'B'
  puts "Not bad!"
when 'C'
  puts "At least you passed."
else
  puts "This is a poor grade!"
end
```

First we get some user input which is presumed to be some single character string like A or F. The next line, `case grade`, says that we are looking at the value of `grade`. Then we go down the list of `when` statements. The first one to evaluate to true has its code evaluated. If `grade` was 'A' then `"Great job!"` would be printed to the screen. If it is anything other than A, B, or C then `"This is a poor grade"` is printed to the screen.

Because we are not using the normal equality operator (`==`) `case` allows us to check for truthiness of other expressions. The following code is valid.

```ruby
grade = gets.chomp.to_i
case grade
when 90..100
  puts "You get an A!"
when 80..89
  puts "You get a B!"
when 70..79
  puts "You get a C."
else
  puts "This is a poor grade!"
end
```

Here we are expecting `grade` to be an integer. When we go down the list of `when` statements the case-equality operator will check to see if `grade` is within the range that we provided. Again, the first statement to evaluate to `true` has the code on its branch evaluated.
