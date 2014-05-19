# What is a Class?

A class is a collection of attributes and methods that describe the behavior of an object. What is an object? An object is an *instance* of a class and in Ruby *everything* is an object. That is a bit circular so let's take a look at a few objects that we are familiar with and see what classes they belong to. Call `.class` on each of the following objects:

```ruby
:address    # Symbol
"Ruby!"     # String
1985        # Fixnum
3.14        # Float
[1,2,3]     # Array
{:a => :b}  # Hash
```

When we see that `"Ruby!"` is an instance of the `String` class it means that deep in the Ruby core somewhere there is a class called "String". It is here that methods like `upcase`, `downcase`, `reverse` exist. Because `"Ruby!` is a member of that `String` we can use those methods on it.

As you progress in your studies you'll learn that this simple exercise is actually really useful. Not every class you'll work with is a member of Ruby's core. In frameworks like Ruby on Rails you'll encounter objects created from classes that are native to the framework. Knowing what class an object belongs to is enormously beneficial when trying to determine how to interact with that object.

```ruby
ary = [1, 2, 3, 4, 5]
ary.size
```

Here, `ary` is a variable that stores an *instance* of the `Array` class. The `Array` class contains many methods we can use to get information about an array or manipulate an array (click [here](http://www.ruby-doc.org/core-2.1.1/Array.html) to see a list of methods that can be called on arrays). When we call `size` on `ary` we are using a method that lives in the `Array` class on the object stored in `ary`. `size` is available to be called because the object in `ary` is an instance of the `Array` class.
