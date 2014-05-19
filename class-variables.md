# Class Variables

Class variables are a little like instance variables except that they are available to all objects of a class. This means that if you write a getter method for a class variable you'll get the same value when you call that method on any object of the class. Class variables have the following properties:

- always begin with "@@"
- available across objects of a class
- they are attributes of a class not an object

I think some examples will best describe how this behavior works. Let's add a person counter to our `Person` class. This counter will count the number of times we have created a new `Person` object.

```ruby
class Person
  @@counter = 0

  def initialize(name)
    @name = name
    @@counter += 1
  end

  def name(name)
    @name
  end

  def name=(name)
    @name = name
  end

  def get_count
    @@counter
  end
end
```

Now load this file into IRB and create three new `Person` objects called `gene`, `nick`, and `gilbert`. If you call `get_count` on any of those objects you should always get back the number 3. If you create a new person object called `mike` then `get_count` will return 4.
