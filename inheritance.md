# Inheritance

So now that we know what a class is we should probably have a chat about *inheritance*.

```ruby
class Person
  def initialize(name)
    @name = name
  end

  def name
    @name
  end

  def speak(words)
    puts "Hi, I'm #{@name}"
  end
end

class Singer < Person
  def sing
    puts "R-E-S-P-E-C-T! Find out what it means to me!"
  end
end

aretha = Singer.new("Aretha Franklin")
aretha.speak
aretha.sing
```
