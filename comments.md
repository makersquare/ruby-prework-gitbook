# Comments

A comment is simply a bit of text within your code that is ignored by the interpreter. In Ruby comments are denoted by the number sign: `#`. A comment can be on its own line or at the end of a line but *not* within a line of code. Like your code, comments can be indented. This is useful when you want to leave a note about a particular line of code. Let's have a look at an example.

```ruby
# This is a comment
def add_nums(x, y)
  puts x + y  # This is also a comment
end
```

The text on line 1 is a simple comment and it will be ignored by the interpreter. The comment on Line 3 begins at the `#` and runs to the end of the line. The actual code, `puts x + y` will be properly evaluated.
