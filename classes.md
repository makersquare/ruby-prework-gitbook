# Classes
So far in this book you've heard repeatedly that Ruby is an object-oriented programming language. You've heard plenty about how the number 5 belongs to the `Fixnum` class and how `Fixnum` inherits from `Integer`. In this lesson we'll talk more specifically about what that means. By the end of the lesson you should be able to answer all of the questions in the "Object Oriented Programming" section of The Checklist. A quick review of those questions:

#### Object Oriented Design
- What are classes and why are they important?
- What is an instance variable?
- What is a class variable?
- What are getter & setter methods?
- What is the purpose of the `initialize` method in a class?
- How do you instantiate a new instance of a class?

----

# Preparation

In this chapter we will type out all our code in Sublime Text and run it in the console. Previously we have entered our code directly into IRB but here the code will be too long for that to be an efficient use of your time.

Open up your terminal client. Navigate to a directory where you'd like to practice these exercises and create a file called `class.rb`. Your process may look something like this:

```console
mkdir class_practice
cd class_practice
touch class.rb
```

Here, `mkdir` will make a directory called "class_practice"; `cd` means "change directory" to "class_practice"; `touch` means create a file which we'll call "class.rb". Go ahead and open up `class.rb` in Sublime Text. It will be an empty file. This is where we'll enter all the code for this chapter.

Let's write some basic code in this file and run it in our console. Type the following code into Sublime Text and then save the file: `puts "Ruby is fun!!!"`. In your console type `ruby class.rb`. You should see `Ruby is fun!!!` printed to your screen.

There's another way to run your code that will be better for us in this chapter. If you are in a directory with a file containing code you'd like to play with you can type jump into IRB and type

```ruby
load 'class.rb'
```

Right now `class.rb` only has code to print something to the screen so if you load that file `"Ruby is fun!!!` will be printed to the screen. You'll also see the word `true` printed. That simply means that the file was successfully loaded. If you get an error that you do not understand please contact nick@makersquare.com immediately to get assistance so you can continue with the rest of the chapter. Let's continue.
