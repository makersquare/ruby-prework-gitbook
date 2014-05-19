# Working With Arrays

I'd like to take a closer look at the structure of arrays and how you manipulate them. I mentioned earlier that you can use `Array.new` or `[]` to create a new empty array. There's not a heck of a lot we can do with an empty array so let's put some data in it.

```ruby
# First create a new array
ary = Array.new

# Now we'd like to add the name "Nick" to it
# Ruby gives us a few ways to do this
ary.push("Nick")  #=> ["Nick"]

# Here's another way to add to an array
ary << "is"     #=> ["Nick", "is"]
ary << "funny"  #=> ["Nick", "is", "funny"]
```

Ok, so now we know how to add elements to the end of an array. Unfortunately, I'm not very funny and I don't want to lie so how can I get rid of "funny" from the end of `ary`? Ruby has a method called `pop` which is basically reverses the effect of `push`. It pops the last element off of the array. The return value of `pop` is the element it popped off. Let's use pop to get rid of "funny" and then let's add the number `28` to the end.

```ruby
ary.pop    #=> "funny"
ary        #=> ["Nick", "is"]
ary << 28  #=> ["Nick", "is", 28]
```

Now we've got an array with strings and a number as its elements. Pretty cool stuff. Now that we know some basic ways of adding and removing elements from an array let's talk about accessing those elements. If you want to access the first element of an array there is a really simple way of doing it: `first`! Try it out on the array `ary` we created. It should return the string "Nick". Now take a wild guess as to how you'd access the last element of an array... If you guess `last` you are correct. Try `ary.last` in IRB to see that you get the number `28`.

Now `first` and `last` are great but they ignore everything in between. That is where indexing comes in. Each element of an array is assigned an index based on its position in the array. Indeces count up one at a time like normal counting. The important part to note is that the first index, that is the index representing the first element of the array, is 0. Let's create a new array in IRB and have a look at how indeces work:

```ruby
people = ["Mike", "Nick", "Clay", "Osei"]
people.size    #=> 4
people.first   #=> "Mike"
people.last    #=> "Osei"

# Now using an index...
people[0]  #=> "Mike"
people[1]  #=> "Nick"
people[3]  #=> "Osei"
```

When using an index to access elements from an array we start with 0 when counting from the beginning. This is why `people[1]` returns `"Nick"` and not `"Mike"`. Even though there are four elements in the array the last element is at index 3. Now that we understand how indeces work it should be noted that you can create ranges to access groups of elements in an array with the indeces as the boundaries of the range. Let's have a look at an example:

```ruby
# Create a new array
people = ["Mike", "Nick", "Clay", "Osei", "Shehzan", "Gene", "Gilbert"]

# Access the second and then the fifth element
people[1]  #=> "Nick"
people[4]  #=> "Shehzan"

# Access the the second and fifth and everything between
people[1..4]  #=>  ["Nick", "Clay", "Osei", "Shehzan"]
```

You'll see that the the range `1..4` accesses all of the elements from index 1 to index 4 *inclusive*. What makes it inclusive? The `..` tells the Ruby intepreter to include the index 4. If you used three dots like this: `1...4` this would *not* include the value at index 4. Play around a bit with this in IRB.
