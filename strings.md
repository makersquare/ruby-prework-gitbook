# Strings

By now you've certainly see plenty of strings in Ruby and so we'll keep this section brief. Strings can be denoted in a variety of different ways but the two main ones with which you'll be mostly concerned are double quoted and single quoted strings.

```ruby
'MakerSquare!' #=> Single quoted string
"MakerSquare!" #=> Double quoted string
```

You may be confused as to when you should use double quoted vs single quoted strings. I'll explain the benefits of both and you can decide which one is better for your particular use case.

Double quoted strings allow you to do and not do certain thing that may be advantageous to you. The first, and most common, reason to use double quotes for strings is to use something called *string interpolation*. String interpolation is the use of a Ruby expression inside a string. Try this in IRB:

```ruby
puts "Five plus two is #{5+2}"
```

You'll see that we put the expression `5+2` inside of `#{}` and it was evaluated and added to the string. That is how string interpolation works. You put just about any expression inside of a string so long as the result of the expression can have `.to_s` called on it. `.to_s` simply converts a Ruby object from whatever it is into a string.

Another time you may want to use a double quoted string is for a string like this:

```ruby
puts "I loved Nick's comments on 'integers' and 'floats!'"
```

Here we used single quotes as part of the string we wanted to print. If you do not use double quotes for strings that have single quotes as part of the string you have to do this:

```ruby
puts 'I loved Nick\'s comments on \'integers\' and \'floats!\''
```

The backslashes are called escape characters. They tell the Ruby interprester that the next character is not part of the program code but actually part of the string itself. This is a perfectly valid thing to do and some people dont mind it. I think it's a little verbose and can make your strings funny looking.

There is one very good reason to use single quoted strings any time you are not using string interpolation or single quotes within strings. Debugging. If you have many strings that interpolate and many that don't it is easier to spot and skip over the ones that don't contain any code if they are single quoted. That is a personal preference for me when dealing with large codebases. You can find a style that suits your needs best.

Let's have a look at some of the commonly used methods on strings.

```ruby
'lol'.upcase          #=> "LOL"
'QUIET'.downcase      #=> "quiet"
'austin'.capitalize   #=> "Austin"
'racecar'.reverse     #=> "racecar"
'MakerSquare'.length  #=> 11
```

These methods all do what you'd expect them to do. That is the beauty of Ruby. There are many more methods that can operate on strings. What do you think happens if you try to add two strings together with `+`? Yes, `+` is a method from when we were working with numbers, however, it also is a method in the `String` class as well. Try out the following in IRB:

```ruby
puts 'I love ' + 'MakerSquare!'
```

Pretty predictable. I'd like to cover one last method from the `String` class before we move on. The method is called `split` and it can take a single optional argument. Let's try it out in IRB:

```ruby
'Ruby is cool'.split  #=> ["Ruby", "is", "cool"]
```

The split method, when called without its optional argument, will take a string, split it at each instance of white space, and then return a new array. Everything between some white space becomes it's own element in the array. You may be wondering, "what's the deal with this optional argument? If it's there, what does it do?" Very good question. The optional argument can be either another string or something we will discuss later called a regular expression. I think an example will best describe the behavior. Type the following into IRB:

```ruby
'MakerSquarexisxcool!'.split('x')  #=> ["Ruby", "is", "cool"]
```

You'll see that we have a weird string that looks familiar but with x's instead of spaces. Because we passed in the string 'x' the `split` method will now split the string anywhere it finds an 'x'. Notice that just like with the spaces the 'x' is discarded and only the strings between the 'x's are kept in the array.

So that brings us to arrays. What on earth is an array?
