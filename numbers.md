# Numbers in Ruby

Every programming language accounts for various data types. In all programming languages numbers fall into at least two data types: integers & floats. In Ruby integers like 0, 5, -53, and 31337 are all instances of the `Fixnum` class. The `Fixnum` class is where the method `+` resides. Beause `5` is a `Fixnum` object we can call `+` on it.

What other methods do you think you can use on the `Fixnum` class? Let's explore a couple others. We'll start with multiplication because it works pretty much as you'd expect it to. Type the following into IRB:

```ruby
2*3*4
2*3*4.0
```

You'll notice that you received the same answer for both but with slightly different levels of precision. It may seem obvious but it is worth noting that `24` is in fact equal to `24.0` even though they look different (one is an instance of the `Fixnum` class while the other is an instance of `Float`). Let's have a look at the affect of this behavior when using the division method:

```ruby
7/2
7/2.0
```

Now this is very different. In our heads it is easy to understand that seven divided by two is actually `3.5` but Ruby didn't get that. That is because if you pass two `Fixnum`s to the division method, `/`, it will return a value that is also a `Fixnum`. However, if you pass it a `Fixnum` and a `Float`, it will divide with more precision and provide the value you expected.

The last mathematical operator I'd like to look at is called the *modulo* operator. It is represented by the `%` character. Type the following into IRB:

```ruby
5 % 2
9 % 7
8 % 5
10 % 2
```

This behavior may seem a little odd at first but it is in fact very simple. The `%` operator divides the left number by the right number and returns the remainder. In the case of  `5 % 2` the number 2 is divided evenly into the number 5 two times and has a remainder of 1. In the case of `10 % 2` the number 10 can be divided by 2 evenly five times with a remainder of 0. This works with floats as well. Try `5.5 % 2` in IRB.


Note:
There are other classes than `Fixnum` and `Float` that different types of number are instances of. Fractions like `(5/3)` belong to a class called `Rational` and complex numbers belong to... you guessed it: the `Complex` class.

The Ruby prework will only be concerned with the `Integer`s and `Float`s so if the other two confused you don't worry about it. If you'd like to know more about all of these classes check out the official Ruby documentation on the class all of these classes belong to. It's called `Numeric`. [Click here](http://www.ruby-doc.org/core-2.1.1/Numeric.html). See the end of the lesson for a closer look at the Ruby object model. It explains the hierarchy of all these different classes in more detail.
