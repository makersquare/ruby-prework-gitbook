# Hash Methods


We've already learned that you can use square brackets, with a key inside, to access values in a hash. If the key you entered doesn't exist the interpreter will return `nil`. This can be a problem if you are trying to capture that value and save it to a variable for use later because your variable will be set to `nil`. Fortunately, Ruby allows us to inspect a hash to see if it has the key we are looking for.

```ruby
ages = {
  "nick" => 28,
  "kate" => 23,
  "atlas" => 3,
  "maple" => 4
}

ages.has_key?("nick")  #=> true
ages.has_key?("bob")   #=> false
```

