# Cookbook App

In this section we are going to implement a basic cookbook application. The application will hold Recipes and has instance variables, it will have initialize methods, attr_accessors and interaction between classes. Some of this will be quite a bit more advanced than what you completed in the Car exercise. The goal of this lesson is to show you how classes can encapsulate data and even other classes.

Remember: after you've created a new method it is a good idea to commit your code with git. Your commit message should be something informative like "Implemented the add_recipe method which addess recipes to the Cookbook class."

----

### How this works

In this exercise we'll write our code in a file called `cookbook.rb` file using Sublime Text. You can save the file in the directory of your choice. Going forward I'll give you some test code and it is your job to build out the class attain the needed functionality. Whenever there is an expected output for a piece of code I'll place it as a comment either next to the code or on the next line.

----

### Let's go!

Here is the first chunk of code you need to make functional:

```ruby
mex_cuisine = Cookbook.new("Mexican Cooking")
burrito = Recipe.new("Bean Burrito", ["tortilla", "bean"], ["heat beans", "place beans in tortilla", "roll up"])
```

As you can see, this code requires you to create two new classes: `Cookbook` & `Recipe`. For this exercise you can create both of these classes in the `cookbook.rb` file.

Create an `initialize` method for the `Cookbook` class and set its parameter to `title`. When you're finished you should have something that looks like this:

```ruby
class Cookbook
  def initialize(title)
    @title = title
  end
end
```

Now do something similar for the `Recipe` class but this time the initialize method should take three parameters: `title`, `ingredients`, and `steps`.

Now test your code in IRB. After you've loaded `cookbook.rb` you can copy and paste the test code directly into IRB.

As you proceed through the exercise you'll need to exit and re-enter IRB each time in order to prevent IRB from creating unintended errors as it holds onto previously run code in its memory.

----

### Getter Methods

Here is the new test code; I've added four new lines:

```ruby
mex_cuisine = Cookbook.new("Mexican Cooking")
burrito = Recipe.new("Bean Burrito", ["tortilla", "bean"], ["heat beans", "place beans in tortilla", "roll up"])

puts mex_cuisine.title # Mexican Cooking
puts burrito.title # Bean Burrito
p burrito.ingredients # ["tortilla", "bean", "cheese"]
p burrito.steps # ["heat beans", "heat tortilla", "place beans in tortilla", "sprinkle cheese on top", "roll up"]
```

The methods used in the new test code allow us to get the values of the instance variables we set in the `initialize` methods. That's why they're called getter methods!

For the `Cookbook` class, the title getter method would look like this:

```ruby
class Cookbook
  def initialize(title)
    @title = title
  end

  def title
    @title
  end
end
```

Now create the getter methods for the instance variables we set in the `initialize` method of the `Recipe` class. Save your code and the hop into IRB to validate your code with the new test code.

Question: why do you think we use `p` instead of `puts` in the test code? Go into IRB to see how `puts [1,2,3]` is different from `p [1,2,3]`.

----

### Setter Methods

It is now time to create our setter methods. Here is the new test code. The last two lines are new.

```ruby
mex_cuisine = Cookbook.new("Mexican Cooking")
burrito = Recipe.new("Bean Burrito", ["tortilla", "bean"], ["heat beans", "place beans in tortilla", "roll up"])

puts mex_cuisine.title # Mexican Cooking
puts burrito.title # Bean Burrito
p burrito.ingredients # ["tortilla", "bean", "cheese"]
p burrito.steps # ["heat beans", "heat tortilla", "place beans in tortilla", "sprinkle cheese on top", "roll up"]

mex_cuisine.title = "Mexican Recipes"
puts mex_cuisine.title # Mexican Recipes
```

Note how `mex_cuisine.title = "Mexican Recipes"` changed the output of `cuisine_cuisine.title` to be `"Mexican Recipes"` instead of `"Mexican Cooking"`.

How would you write a method to enable that functionality? That method is called a setter method because it sets or changes the value of something.

The syntax for it looks like this:

```ruby
def title=(new_title)
  @title = new_title
end
```

Note the `=` at the end of the method name. Yes the `=` is part of the name and there is no space between it and `title`. Add that method to your `Cookbook` class. Run our test code in IRB and make sure it works.

Let's add the following lines to our test code and then add the necessary code to the `Recipe` class to make it work.

```ruby
burrito.title = "Veggie Burrito"
burrito.ingredients = ["tortilla", "tomatoes"]
burrito.steps = ["heat tomatoes", "place tomatoes in tortilla", "roll up"]

p burrito.title # "Veggie Burrito"
p burrito.ingredients # ["tortilla", "tomatoes"]
p burrito.steps # ["heat tomatoes", "place tomatoes in tortilla", "roll up"]
```

Test it out in IRB.

----

### attr...what?

You probably noticed that writing all those getter and setter methods is pretty tedious. Fortunately, Ruby has some shortcuts for us: `attr_reader`, `attr_writer`, and `attr_accessor`.

- `attr_reader` is equivalent to writing a getter method
- `attr_writer` is equivalent to writing a setter method
- `attr_accessor` is equivalent to writing getter *and* setter methods

You can add them to your class like this:

```ruby
class Recipe
  attr_reader :title
  attr_writer :steps
  attr_accessor :ingredients

  def initialize(title, steps, ingredients)
    @title = title
    @steps = steps
    @ingredients = ingredients
  end
end
```

`attr_reader :title`, `attr_writer :steps`, and `attr_accessor :ingredients` in the code above are equivalent to these lines of code:

```ruby
# attr_reader :title replaces this getter method
def title
  @title
end

# attr_writer :steps replaces this setter method
def steps=(value)
  @steps = value
end

# attr_accessor :ingredients replaces both getter and setter methods below
def ingredients
  @ingredients
end

def ingredients=(value)
  @ingredients = value
end
```

Go ahead and replace all of your getter and setter methods with these shortcuts. Be sure to test your code in IRB and then commit your changes with git.

----

### Getting everyone talking

So now we've set instance variables for when we use our class to make a new object, and we've set up getter and setter accessors that allow us to modify and view these instance variables. How do we go about actually making these objects (instances if our classes) talk to each other?

By using methods! Not only can a method take in strings and arrays as arguments, it can also take objects themselves as arguments.

Let's try using an object as an argument. We've added 3 lines of code to the bottom of our test code:

```ruby
mex_cuisine = Cookbook.new("Mexican Cooking")
burrito = Recipe.new("Bean Burrito", ["tortilla", "bean"], ["heat beans", "place beans in tortilla", "roll up"])

puts mex_cuisine.title # Mexican Cooking
puts burrito.title # Bean Burrito
p burrito.ingredients # ["tortilla", "bean", "cheese"]
p burrito.steps # ["heat beans", "heat tortilla", "place beans in tortilla", "sprinkle cheese on top", "roll up"]

mex_cuisine.title = "Mexican Recipes"
puts mex_cuisine.title # Mexican Recipes

burrito.title = "Veggie Burrito"
burrito.ingredients = ["tortilla", "tomatoes"]
burrito.steps = ["heat tomatoes", "place tomatoes in tortilla", "roll up"]

p burrito.title # "Veggie Burrito"
p burrito.ingredients # ["tortilla", "tomatoes"]


mex_cuisine.recipes # []
mex_cuisine.add_recipe(burrito)
p mex_cuisine.recipes # [#<Recipe:0x007fbc3b92e560 @title="Veggie Burrito", @ingredients=["tortilla", "tomatoes"], @steps=["heat tomatoes", "place tomatoes in tortilla", "roll up"]>]
```
