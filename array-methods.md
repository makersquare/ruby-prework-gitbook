# Array Methods

Let's have a look at a few more commonly used Array methods. A time may come where you are given an array of arrays that looks something like this: `[1, 2, [3, 4, [5]]]`. That is an array within an array within an array (insert Inception joke here). If you are concerned with only the values within these arrays and the actual structure here is getting in the way then Ruby has a solution for you!

```ruby
nest = [1, 2, [3, 4, [5]]]
nest.flatten   #=> [1, 2, 3, 4, 5]
nest           #=> [1, 2, [3, 4, [5]]]
nest.flatten!  #=> [1, 2, 3, 4, 5]
nest           #=> [1, 2, 3, 4, 5]
```

The `flatten` method basically smushes all of the arrays within arrays down into a single array and returns that new non-nested array. However, it only returns the new array. It does not change the original value. If you would like to mutate that original value in place and not have to assign it to a new variable you can use `flatten!`. The `!` at the end of the method name is common in Ruby. Other methods that have it are `map`, `upcase`, `downcase`, as well as a few others.

I'd like to talk about three more array methods before we move on to Ruby's other commonly used data structure. The three methods are: `shift`, `unshift`, and `+`. First I'll show you how they work and then explain the behavior.

```ruby
b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
a = b.shift(5)  #=> [1, 2, 3, 4, 5]
b               #=> [6, 7, 8, 9, 10]
c = a + b       #=> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
c.unshift(0)    #=> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
c               #=> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

So, there's quite a lot going on here but it's really some pretty simple behavior. Let's start from the top. We create a new variable called `b` and assign it an array containing the numbers 1 through 10. On the second line we use the method `shift` with the argument `5` on the array in `b`. When you call `shift` with a number 'n' it takes the first 'n' elements from that array and returns them in a new array.

It is important to note that it literally removes them from the original array much like `pop` takes the last element off of the array.

So on line two we didn't just shift the elements out of the array; we also saved them to a new variable called `a`. You can see on line 3 that the first 5 elements are in fact missing from the original array. On line 4 we use the new `+` method to put the two arrays back together and save it in a new variable called `c`.

Finally on line 5 we use the `unshift` method to add the element `0` to the *beginning* of the array. Earlier we saw how we can use `push` or `<<` to append to the end of an array. `unshift` allows you to *prepend* to an array.

That's it *for now*.
