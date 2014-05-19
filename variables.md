# Variables

So far we have been dealing with objects directly. When we've wanted to add two numbers together we've simply done: `5 + 9`. When we've wanted to sort an array we've had to type out `[5, 3, 1, 4, 2].sort`. This isn't very efficient and is prone to typos. Variables fix the problem by allowing us to give an object a name and then call methods on that name instead of the object itself. Let's try it out. Type the following in IRB:

```ruby
my_name = "Nick McDonnough"
my_name
my_name.downcase
my_name.length
my_coworkers = ["Shehzan", "Amanda" ,"Mike", "Gilbert", "Gene", "Emily"]
my_coworkers
my_coworkers.length
sorted_coworkers = my_coworkers.sort
```

The first few seven lines are pretty trivial and do what you'd expect. The string `"Nick McDonnough"` is saved to the variable `my_name` and then when we simply call `my_name` by typing it into IRB. As expected it returns the string `"Nick McDonnough"`. After you assing a value to a variable you can access that value anywhere by simply typing in the variable name.

The last line of that example is very important. In Ruby you do not have to know the exact object when you decide to give it a name by saving it to a variable. You can use an expression! An expression will evaluate to an object and that object will be saved to the variable. Here `my_coworkers.sort` evaluates to the object `["Amanda", "Emily", "Gene", "Gilbert", "Mike", "Shehzan"]`. That object is then given the name `sorted_coworkers`.

Variables can also be reassigned. Try this out in IRB:

```ruby
name = "Nick"
puts name
name = "Mike"
puts name
```

There is one caveat about doing this kind of thing. When working with even a relatively small codebase reusing variable names can get very, very, confusing. My rule of thumb is that if you want to mutate some value that is assigned to a variable you should assign the new value to a new variable.
