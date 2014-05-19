# Tools

### IRB

We will also be introduced to the Interactive Ruby Shell. IRB, as it is known, is an interactive environment in your terminal where you can evaluate Ruby code. You should already have IRB installed; if you do not go to [ruby-lang.org](https://www.ruby-lang.org/en/downloads/). You can check if you have IRB installed by simply typing `irb` into your terminal.

```console
irb
```

IRB is a REPL for Ruby code. REPL stands for Read, Evaluate, Print, Loop. What a REPL does is spelled out rather succintly in its name: it Reads a line of input from the user, it Evaluates that line, it Prints the result of the evaluation, and then it Loops back to waiting for more user input. Many languages have REPLs and IRB is one of the most commonly used ones for evaluating Ruby code.

Let's open up IRB and try out a few things.

```ruby
5+9
'lol'.upcase
[1,2,3,4,5].map { |x| x * 5 }
["Nick", "Patrick", "Alex", "Mike"].each do |person|
  puts person
end
```

### Sublime Text

There are very many text editors out there. There are probably even more opinions as to which one is the best. Because of its ease of use and extensability we suggest students start with Sublime Text. Yes, editors like vim and Emacs have excellent features too but I feel that their steeper learning curve could inhibit you over the course of your time at MakerSquare.

Loving the tools you work with is important as a developer and so if you feel the need to try a different editor, or even a different REPL, go for it. There are a lot of fantastic choices out there.
