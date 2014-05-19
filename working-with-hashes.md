# Working with Hashes

#### Creating a new hash

Like arrays there are three ways to create a hash: you can use `Hash.new`, `{}`, or use a method that returns a hash like [`group_by`](http://www.ruby-doc.org/core-2.1.1/Enumerable.html#method-i-group_by).

```ruby
a = Hash.new   #=> {}
b = {}         #=> {}
a == b         #=> true
```

#### Adding a new key/value pair

The following behavior shows the simplest way to add a single key value pair to a hash is like this:

```ruby
hsh = {:texas => "Austin", :new_york => "Albany"}
hsh[:oregon] = "Portland"
hsh   #=> {:texas => "Austin", :new_york => "Albany", :oregon => "Portland"}
```

On line 1 we simply save a hash with two key/value pairs to the variable `hsh`. The first part of line two may look familiar to you. It looks a bit similar to how we'd access the value at the key `:oregon` however it is followed by `= "Portland"`. That second part is what tells the interpreter to save the value `"Portland"` in `hsh` with `:oregon` as its key.

#### Adding many key/value pairs

What if we wanted to add 2, 3, 4, or 100 new key value pairs to an existing hash. The method displayed in the previous section would become tedious. Again, Ruby saves the day with another awesome method from the standard library. This time it's called `merge`. Let's go back to our state capital hash and add a few more.

```ruby
hsh = {:texas => "Austin", :new_york => "Albany"}
hsh2 = {:oregon => "Portland", :idaho => "Boise"}
hsh.merge(hsh2)  #=> {:texas => "Austin", :new_york => "Albany", :oregon => "Portland", :idaho => "Boise"}
```

The `merge` method takes one hash and merges it with another however it will not mutate the original hash it was called on; it will only return a new hash containing key/value pairs from both hashes. If you would like to mutate the original hash to contain all the new values to you'd have to use a `!` just like we did with `flatten!` in the array section. Another important thing to note here, if `hsh2` contained a key that already existed in `hsh` the original value in `hsh` would be overwritten with the new value. **Remember, keys cannot be duplicated in a hash.** If there is a conflict one of the values will be overwritten.
