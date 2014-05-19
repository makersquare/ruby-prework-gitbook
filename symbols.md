# Symbols

Ruby symbols are denoted by a `:` at the beginning of a word and are often used in place of strings. This is because symbols are always unique in the Ruby ecosystem. What this means is that the symbole `:mks` used in one part of your program will have the same `object_id` as `:mks` used somewhere else. This is a little like how there is only one number 5 in the world. If you use a 5 in one method its still the same 5 in another.

```ruby
def first
  puts :nick.object_id
end

def second
  puts :nick.object_id
end

first   #=> 522408
second  #=> 522408
```

Symbols are often used as keys in hashes:

```ruby
dude = {
  :name => "Nick",
  :age  => 28,
  :city => "Austin
}
```
