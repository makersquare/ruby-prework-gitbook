# Nested Hashes

The following is something we call a *nested* hash. It is a hash with some data type as a key, in this case a symbol, and then another hash as the value.

```ruby
person = {
  :name => "Nick McDonnough",
  :age => 28,
  :address => {
    :street => "2520 Elmont St",
    :city => "Austin",
    :state => "TX"
  }
}
person[:name]     #=> "Nick McDonnough"
person[:address]  #=> {:street=>"2520 Elmont St", :city=>"Austin", :state=>"TX"}
```

Here we see that if you access the value of the `:address` key in our nested hash you get another hash back. If you'd like to access a value in that returned hash you do it in the same way you would access a value in a regular hash. Try this out in IRB:

```ruby
person[:address][:city]  #=> "Austin"
```

If you typed everything correctly you should get back the string `"Austin"`. If this is a little confusing think about it this way: `person` is the large nested hash with keys `:name`, `:age`, and `:address`. If you call `[:address]` on `person` you get back a hash. So for all intents and purposes `person[:address]` is a representation of the value at the key `:address` which in this case is another hash. This means we can call `[:city]` on it to get the value in that nested hash.
