# Booleans

Sometimes when evaluating code we need to determine if a given condition is true or false. Ruby provides global values called `true` and `false` which belong to the `TrueClass` and `FalseClass` classes respectively. It is important to note that everything in Ruby technically evaluates to `true` *except* for `nil` and `false`. You'll learn later that this allows for some fun ways of writing conditional statements.

```ruby
5 > 3   #=> true
5 != 3  #=> true
1 == 1  #=> true

9 != 9  #=> false
3 > 5   #=> false
false == true #=> false
```

#### Boolean Operators

Sometimes standard boolean expressions are not appropriate and so the boolean operators allow us to chain them together to come to a new conclusion. The and operator, `&&`, takes two operands and if they both evaluate to `true` then the entire expression evaluates to `true`. The or operator, `||`, also takes two operators and if *either* evaluates to `true` then the entire expression evaluates to `true`. The final boolean operator is called not, `!`. It reverses the truthiness of its operator so if it is passed something that is `true` then `false` will be returned.

```ruby
true && true     #=> true
false && false   #=> false
false || true    #=> true
false || false   #=> false
!true || !false  #=> true
```
