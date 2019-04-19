# Unplugged Activity: PB & J

Here's another example of how functions might be used to define a complex task. Imagine that a parent makes you lunch every day – wouldn't it be nice to delegate this task to a computer? Ask students to imagine a robot that would make them a peanut butter and jelly sandwich (PB & J) every day. What are the steps involved in making a peanut butter and jelly sandwich? Can they write a function that includes all the steps necessary to make a yummy sandwich?

This is a fun activity to do in the classroom but better if you bring in real food!

## Do the activity

### Materials

* A jar of peanut butter** (initially closed)
* A jar of jelly (initially closed)
* A bag of sliced bread (initially closed)
* A plate
* A knife
* A paper towel

### ~ hint

****Caution!**

Check for allergies to peanuts. You can always substitute butter or cream cheese for the peanut butter.

### ~

Write pseudocode for the making of a PB & J sandwich:

* Have students work in pairs to write pseudocode (English language instructions) for making a peanut butter and jelly sandwich. 

This is a pseudocode example from the overview:

![WriteMyName Pseudocode Example](/static/courses/csintro/functions/overview-mary-example.png)

### Execute the instructions

* You, the teacher, will pretend you are the robot.
* Collect all the pseudocode instructions and chose one to perform. The one with the least number of steps is usually a good one to start with, because the students will have made some assumptions about what you, the robot, know how to do.
* Follow the instructions as written. This is your chance to have some fun, usually by following their exact instructions without using "what you know they meant."

**An example run:**

* The first step is often "Open the bread." Feel free to just rip open the bag of bread, because their instructions did not say anything about untying the knot or unclipping the bag opening.
* If the instruction is "Put two slices of bread on the plate," you can put one slice on top of the other, because that instruction did not specify how to place the slices.
* If their next instruction is "Put peanut butter on one slice of bread," you can put the whole peanut butter jar on the bread slice, because they gave no instructions about opening the jar first. 
* If an instruction tells you to do something you simply cannot, like "Use knife to scoop out jelly" yet the jelly jar isn't even open, you can just report a "runtime error" and stop the program.

By the time you have gone through a few steps, or run a couple of programs to the point where they produce an error, the students have gotten the idea that they have left out important steps and also made assumptions about what functions you already know how to perform, and they are asking for their papers back so they can rewrite their pseudocode.

### Rewrite pseudocode into functions

* Give them the chance to rewrite their **MakePB&J** functions and let them know some smaller functions you already know how to perform. For example, if they write "Open jelly jar" or "Take lid off of jelly jar," tell them you already know the **OpenJar** function, so they do not need to write "Grasp lid tightly. Twist lid to the left...."
* Students will then start asking, "Do you know how to..?" to find out what other functions you already know.
* Perform some of their revised functions. Some students are usually happy to consume the results!

### Example functions

#### Main program

`||functions:MakePB&J||` **function**

* `||agent:Open||` bread bag
* Remove two slices of bread.
* Place each slice face down, side by side on the plate.
* `||arrays:OpenJar||` Peanut butter
* `||arrays:OpenJar||` Jelly
* Pick up the knife.
* `||loops:Spread||` Peanut butter on one slice of bread
* `||loops:Spread||` Jelly on the other slice of bread
* Put the knife down.
* Pick up one slice of bread and lay it face down on the other slice of bread.
* Wrap the bread in a paper towel.

#### Helper functions

`||agent:Open||` **function**

* Grasp the end of the bag with the opening.
* Unclip the plastic holder.
* Untwist the wrapping.
* Reach in.

`||arrays:OpenJar||` **function**

* Put one hand on the top lid of the jar and grasp tightly.
* Put the other hand around the base of the jar.
* Repeat until the lid is loose: twist your top hand counter-clockwise.
* Remove the lid of the jar.

`||loops:Spread||` **function**

* With a knife, reach into the jar.
* Scoop out contents.
* Move the knife backward and forward over the bread until the knife is clean.
* Repeat the previous three steps until the bread is completely covered. 

## Challenge: Write a Function for a Task (Can be given as homework)

* Have each student choose a "simple" task, like tying a shoe or brushing their teeth, and as them to write in pseudocode a function to perform that task. 
* Along with their pseudocode, each student should bring in whatever props are necessary to perform their function.
* Select a student's pseudocode and give that function and the props to another student to perform. 
* After watching you the day before, the students are primed to follow the instructions as written!

These exercises help students realize the value of functions as a way to organize their programs, and also how each function can itself include "calls" to smaller functions.

## Additional Challenge: A Cleaning Robot

* How might you program a robot to clean the house? 
* Are there tasks that are common for all rooms of the house? (Vacuuming, dusting)
* Are there tasks that are specific to certain rooms in the house? (Clean the toilet, make the bed)
* Which tasks can you assign to functions? (pickUpStuff, dust, sweep, vacuum) 
* How might you break up the overall task of cleaning a house into specific functions? (**cleanTheKitchen**, **cleanTheLivingRoom**, **cleanBathrooms**, etc.)

Have students write two different examples for cleaning a room in the house by using pseudocode.