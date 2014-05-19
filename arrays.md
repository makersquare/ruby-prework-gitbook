# Arrays

Arrays are Ruby's most basic data structure. They essentially are heterogenous containers of data. This means you are given a ton of freedom with what you can put inside an array. A non exhaustive list of things that can go inside an array:
- strings
- symbols
- numbers
- other arrays

Arrays can be created three different ways, `Array.new`, `[]`, or as the result of a method, like `.split`, that returns an array (tehcnically the first two ways are both methods that return empty arrays). The methods that operate on arrays are plentiful and some can be quite complex. Let's have a look at some of the simple ones.

```ruby
['a', 'b', 'c', 'd'].length  #=> 4
[5, 3, 1, 4, 2].sort         #=> [1, 2, 3, 4, 5]
```

Here the `length` method works similarly to the one we used earlier on a string. It counts the number of elements in the array and returns an integer value. There is another array method that mimics this behaviour: `size`. We call `size` an *alias* of `length`.

The `sort` method does exactly what it sounds like. It sort's the array! What do you think happens if you try to sort an array of strings like `['Nick', 'Gilbert', 'Alex', 'Osei']`. Go ahead. Try it.

As you can imagine, typing out arrays by hand like we just did can get pretty tiring. It's also a bit dangerous if you want to use the same data repeatedly because you could mistype something. Fortunately Ruby has a solution to this problem.
