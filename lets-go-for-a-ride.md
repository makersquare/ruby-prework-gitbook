# Let's Go for a Ride

In this exercise I'll walk you through the process of creating a new class. Pay close attention because you'll need to do this all on your own in the next section.

I want to create a class that can simulate a car. I'll list out the specs first and then give step by step instructions on how to attack the problem.

- I want the car to keep track of it's position and how much gas it has
- When I call the method setup on the car, it should set the position to 0 and gas to 10 (gallons)
- I should be able to drive the car and tell it how many miles to drive. The car should adjust it's position and gas mileage here
- I want the car to be able to fill up gas and print out how much the gas cost

----

### Create a Ruby Project

First we'll need to create a new directory for our project; you can call it `car_exercise` or something similar if you'd like. In that folder create a file called `car.rb` (you can use the UNIX command `touch`). In that file create a new class called `Car`. We'll leave it empty for now. Load the class into IRB and create a new instance of the `Car` class to make sure it works. If you see something sort of cryptic that looks a little like `#<Car:0x007f8214ab6dd0>` then you're in great shape.

Back in your `car.rb` file let's add a method to the `Car` class called `get_info`. It should only have a single line that reads `return "I'm a car!"`.

Protip: in Ruby the last line of a method is the return value of the method and so you can actually leave out the `return` keyword.

Now if you reload `car.rb` in IRB and create a new instance of `Car` you can run `get_info`. You should see `"I'm a car!"` printed to the screen.

Let's also create a method called `setup`. We'll use this method to set two instance variables: `@fuel` should be set to 20 and `@distance` should be set to 10. While we're at it let's edit the `get_info` method to tell us something a little more interesting. Instead of just being told "I'm a car!" rewrite the sentence to read:

"I'm a car. I've driven 10 miles and have 5 gallons of gas left."

You may have guessed that the `get_info` method will not run properly now unless you first call `setup`. Go ahead and try it. The error message you see is a common one so do familiarize yourself with it.

----

### Initialize

We have a pretty serious problem with the way we have constructed the `Car` class. The problem is that if someone wanted to use this class there would be no way for them to know that they'd first have to run this weird `setup` method before they could get any info about the car.

As usual Ruby comes to our rescue with the `initialize` method. It is a method that is run automatically when a new instance of our class is created. So let's rename `setup` to `initialize`. Note: it is best practice to have the `initialize` method be the first method in a class. If you want to see this new method in action type `puts "this ran automatically!"` somewhere inside `initialize`. When you run `Car.new` now you should see that string printed to the screen.

----

### Drive!

A car wouldn't be a car if it didn't drive so let's write a `drive` method that takes one input, the distance driven. The drive method should then increase `@distance` by the amount passed to `drive` and then reduce `@fuel` at a rate of 20 miles per gallon.

To test this out follow these steps:

1. Load the files in IRB
2. Create 2 cars: `car_a` & `car_b`
3. Print each car
4. Drive car_a 10 miles
5. Run `get_info` for both cars
6. Drive both cars a distance of your choice. Make sure the values you get from `get_info` make sense.

What do you think would happen if you drove either car 1000 miles? You may get s value from `get_info` that doesn't make sense. How would you go about preventing that? Try making it so that it's not possible to drive the car after it has reached 0 gallons of fuel.

### Fuel Up!

In light of our new limitation create a method called `fuel_up` that determines how many gallons of gas the car needs to get to its capacity: 20 gallons. Presume that this car exists in some fantastic utopia where fuel only costs $2 per gallon. When you call `fuel_up` it should print a message to the screen which tells you the total cost to fill up the tank.

When you're finished commit your code and push it to GitHub.

Congratulations on creating your first functional class! Take a few minutes off before proceeding to the next exercises.
