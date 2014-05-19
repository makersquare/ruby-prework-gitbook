# The 'class' Constructor

To create your own class you use the word `class` followed by the name of the class, which is always capitalized. You denote the end of your class with the keyword `end`.

```ruby
class Person
end
```

That's it! We now have a `Person` class. When you want to create a new instance of a class you generally will use the `new` method. This method belongs to the Ruby core and by default any class you create will inherit it. To create a new instance of our newly created `Person` class we'd simply write:

```ruby
nick = Person.new  #=> #<Person:0x007fc0a995ba70>
```

The return value of creating a new instance of our `Person` class looks a little weird but it is normal. This is the way that Ruby textually represents an object that cannot be easily printed to the screen like a string would be.

#### The `initialize` method

When you call `new` on a class Ruby looks to see if you wrote an `initialize` method. If you did it runs the method automatically and passes to it any arguments you included in your `new` call. This gives you the ability to pass some arguments in to your class to be saved or manipulated at the moment it is created.
