# Hashes

Hashes are similar to arrays except for all the ways that they are different. I kid, I kid. At first hashes may seem similar to arrays because they are a place you can store information but you will learn that they are very different and those differences are extremely important.

Hashes are denoted with curly braces in Ruby as such: `{}`. You can access values in a hash with square brackets just like with an array however what goes inside is not the index of the element you are looking for but the *key* associated with the *value* you are looking for. Let's have a look at the basic structure of a hash that we'll call `person`.

```ruby
# Create a new hash with some data already in it
person = { :name => "Nick", :age => 28, :city => "Austin" }

# Access the value at :city
person[:city]  #=> "Austin"

# How big is `person`?
person.size    #=> 3
```

The last line `person.size` returned `3`. This may be confusing because that hash certainly looks bigger than 3. In fact I see 3 symbols used for keys and 3 strings or integers used for values. That balance, 3 keys and 3 values, always exists in a hash and it is why the size of the hash is 3. To describe the size of this hash we would say that it has 3 *key/value pairs*. Every key in a hash must have a value, even if it is `nil` or `false`, and a value cannot exist in a hash without a corresponding key.

So what data types might we be able to use as keys and values in a hash? The answer is simple: literally anything. You can use a number as a key or value, you can use a string as a key or a value, you can even use data structures like arrays or hashes themselves as keys or values though it is probably not advisable to use an array or a hash as a key in a hash. Arrays are frequently used as values in hashes as are other hashes. It is pretty common to see a hash as a value in another hash too.
