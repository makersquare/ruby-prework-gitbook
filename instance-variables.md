# Instance Variables

In the previous segment we learned about a method called `initialize` that runs automatically when we call the `new` method on a class. So far we only have a pretty boring `Person` class that does nothing. Since the `Person` class is a blueprint for future `Person` objects we can predict that those object may need names just like real people. Let's add that functionality now.

```ruby
class Person
  def initialize(name)
    @name = name
  end
end

nick = Person.new("Nick")
```

Now when we call `Person.new` we can pass in a name like this: `Person.new("Nick")`. The `initialize` method takes one parameter called `name` and then... what on Earth is `@name`? That is an instance variable. An instance variable has the following properties:

- always begins with an "@"
- available only within the instance in which it was created
- available to *any* method within that instance

The key thing here is that two different objects of the same class are allowed to have different values for their instance variables. The value of those variables is stored in the object itself. Another important thing to note is that instance variables are private by default. This means that they are invisible outside of the object unless you write some code to expose them.

So far we have created a `Person` class which can be instantiated with a name. The name is saved to an instance variable called `@name`. We know now that `@name` is invisible outside of the object. So let's write a method that allows us to see the value of `@name`.

```ruby
class Person
  def initialize(name)
    @name = name
  end

  def get_name
    @name
  end
end

nick = Person.new("Nick")
nick.get_name              #=> "Nick"
```

Now we can call our fancy new `get_name` method and it will return the value saved in `@name`. Very cool. What if when we created a new instance of the `Person` class we spelled the name wrong? As the code stands now we have no way of changing it. Let's write another method called `set_name` that changes the value of `@name` instead of just returning it.

```ruby
class Person
  def initialize(name)
    @name = name
  end

  def get_name
    @name
  end

  def set_name(name)
    @name = name
  end
end

nick = Person.new("Nikc")
nick.get_name              #=> "Nikc"
nick.set_name("Nick)
nick.get_name              #=> "Nick"
```

Fantastic! We can now access and change the value of an instance variable that was previously invisible to us. You may notice that this isn't a very Ruby-like way to retrieve or set a variable. In the past when we wanted to see a value in a variable we just wrote the variable name into IRB and if we wanted to set its value we did something like `some_var = "some value"`. We can recreate that functionality very easily with something called "getter" and "setter" methods. I'll refactor our code to follow the proper convention

```ruby
class Person
  def initialize(name)
    @name = name
  end

  def name
    @name
  end

  def name=(name)
    @name = name
  end
end

nick = Person.new("Nick")
nick.name               #=> "Nick"
nick.name = "Nicholas"
nick.name               #=> "Nicholas"
```

For the getter method all we have done really is rename the method `get_name` to the actual name of the instance variable. The setter method is just as simple but looks a little odd. Notice the `=` at the end of the name of the method. That equal sign tells Ruby to allow us to do things like `nick.name = "Nicholas"`. Without the equal sign on the end of the method name we'd have to write our setter method like we did before and that's no fun.

Notice how the `@name` instance variable is available in all three methods we have written for the `Person` class. This is what I was referring to earlier when I said that instance variables are available to any method within the instance. `@name` will have the same value in every method unless you change it somewhere.
