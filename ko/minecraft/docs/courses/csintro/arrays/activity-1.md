# Activity: We Built a Zoo

You can store animals in an array and spawn them wherever you like. We’ll use this capability to build a fenced-in animal pen and create an instant zoo anytime we want. When this project starts up, it will create an array and fill it with animals of your choice.

This project will feature two commands:

* "pen": Call this first to command the Builder to create a fenced-in pen around your position, so the animals don’t escape.
* "zoo": At this command, MakeCode will go through your array and spawn two animals of each type, within the pen.

## Do the activity

### Create the project

1. Create a new MakeCode project called "Zoo".

2. In `||loops:LOOPS||`, there is an `||loops:on start||` that will run its commands once, as soon as the project starts up. Drag that block into the coding Workspace.

### ~ hint

`||loops:on start||` runs when the program starts. This can be a pain at times because you are testing code or want to restart the program but may not understand why your program is not working. Use the buttons in the lower left-hand corner to restart your code when building code that relies on `||loops:on start||`.

1. Click the stop button in the lower left-hand corner of your code connection window.

![Stop Code](/static/courses/csintro/conditionals/stop-code.png)

2. Next, you will need to restart the coding environment. Click the play button. If the play button is not on then your code will not run in Minecraft.

![Play](/static/courses/csintro/conditionals/playbutton.png)

### ~

3. From `||variables:VARIABLES||`, click the **Make a Variable** button.

4. Name this variable `animalarray`, and click **Ok**.

![Make the 'animalarray' variable](/static/courses/csintro/arrays/make-animalarray-variable.jpg)

### Make an array for animals

5. From `||variables:VARIABLES||`, drag `||variables:set||` into the On start block.

6. Using the drop-down menu in `||variables:set||`, select the `animalarray` variable.

7. Click on the Advanced tab in the Toolbox to display the `||arrays:ARRAYS||` Toolbox drawer.

8. From `||arrays:ARRAYS||`, drag a `||arrays:create array with||` into `||variables:set "animalarray" to||`.

![Pick the create array block](/static/courses/csintro/arrays/create-array-block.jpg)

### Add animals to the array

9. Click the Plus **(+)** sign on `||arrays:create array with||` to add 7 more slots in your array. The total length of your array should be 8.

10. From `||mobs:MOBS||`, drag an Animal block into the first slot of `||arrays:create array with||`.

11. Populate the rest of your array with animal blocks. You can right-click on `||mobs:animal||` and select **Duplicate** to make copies of this block.

![Duplicate the animal block](/static/courses/csintro/arrays/duplicate-animal.jpg)

### Pick your animals

Create a zoo with 8 different types of animals. Be aware that certain animals will eat other animals! For example, ocelots and chickens don’t get along very well. Think about what kind of zoo you want, and plan accordingly.

12. Using the drop-down menus in the `||mobs:animal||` blocks, select different types of animals in your array.

![Select the animal types for array items](/static/courses/csintro/arrays/select-animal-types.jpg)

### Let's have an animal pen

Now that you have your Animal Array set up, let’s work on creating a fenced-in enclosure for your zoo. You will use the `||builder:BUILDER||` blocks for this. The Builder is like an invisible cursor in the game that can place blocks along a path very quickly. You will direct the Builder to go to a point in the southeast corner, and create a mark, which is an invisible point of reference. Then you will give it a series of commands to make it trace out a square. Finally, the builder is able to place fences along this path.

13. From `||player:PLAYER||`, drag an `||player:on chat command||` block to the Workspace.

14. Rename the command "pen".

15. Click on the Advanced tab in the Toolbox to display the `||builder:BUILDER||` Toolbox drawer.

16. From `||builder:BUILDER||`, drag `||builder:builder teleport to||` into `||player:on chat command "pen"||`.

### Find a place for the pen

Recall that Minecraft coordinates are always specified in **X**, **Y**, **Z** coordinates where **X** is west to east and **Z** is north to south. We want the Builder to start in the northeast corner of the pen in relation to the player, so go ahead and change the coordinates to specify a location 5 blocks east and 5 blocks north of your position.

17. In `||builder:builder teleport to||`, change the position values to `(~5, ~0, ~-5)`.

![Pick out the builder teleport block](/static/courses/csintro/arrays/builder-teleport.jpg)

### Set the starting mark

Let’s make sure the Builder is facing the right way so that it draws the pen around you. After the builder is facing the correct direction, you can then have it place a starting mark.

18. From `||builder:BUILDER||`, drag `||builder:builder face||` out and under `||builder:builder teleport to||`. The default 'face West' is fine.

19. Next, from `||builder:BUILDER||`, grab a `||builder:builder place mark||` to put after the `||builder:builder face||`.

### Draw the outline of the pen

Now we’ll simply have the Builder draw a square.

20. From `||loops:LOOPS||`, drag a `||loops:repeat||` loop and place it after `||builder:builder place mark||`. A square has four sides so repeating four times is great.

21. From `||builder:BUILDER||`, drag a `||builder:builder move||` into the `||loops:repeat||` loop.

22. Type `10` into `||builder:builder move||` to make the sides of your pen 10 blocks.

23. From `||builder:BUILDER||`, drag `||builder:builder turn||` after the `||builder:builder move||` block.

### Put up your fences

The last step is to have the Builder place fences along the square it traces.

24. From `||builder:BUILDER||`, place a `||builder:builder trace path from mark||` after the `||loops:repeat||` loop.

25. Using the drop-down menu in `||builder:builder trace path from mark||`, select an Oak Fence.

Your code should look similar to this:

```block
player.onChat("pen", function () {
    builder.teleportTo(positions.create(5, 0, -5))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(SixDirection.Forward, 10)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(blocks.block(Block.OakFence))
})

```

### Try the *"pen"* command

Now, open up a Flat World in the Minecraft game, and type "pen" in the chat window. You should see a pen being built all the way around you! For an extra challenge, you might try to get the Builder to add a fence gate.

![Pen Built](/static/courses/csintro/arrays/pen.jpg)

### Get ready to release the animals

Now comes the fun part. The array is loaded up with animals, the pen has been built... it’s time to let them loose! For this command, we will simply go through the entire array and for each animal in the array, we will spawn two of them a few blocks away from you but still within the pen.

26. From `||player:PLAYER||`, get an `||player:on chat command||` and rename it "zoo".

27. From `||loops:LOOPS||`, drag a `||loops:for element||` into your `||player:on chat command "zoo"||`.

28. In the `||loops:for element||`, use the drop-down menu for the **2nd slot** to select `animalarray`.

![Select 'animalarray' variable](/static/courses/csintro/arrays/select-animalarray.jpg)

### Let them go!

29. From `||mobs:MOBS||`, drag a `||mobs:spawn animal||` block and place it inside `||loops:for element||`.

30. From `||variables:VARIABLES||`, drag the value variable into the `||mobs:spawn animal||` block, replacing the default chicken animal.

31. Adjust the coordinates in `||mobs:spawn animal||` to `(~3, ~0, ~0)`, so the animals will spawn a few blocks away from the Player.

32. To create pairs of animals, right-click on the `||mobs:spawn animal||` block to Duplicate it. You could also use a loop here if you choose.

Your code should look similar to this:

```block
let animalarray: number[] = []
player.onChat("zoo", function () {
    for (let value of animalarray) {
        mobs.spawn(value, positions.create(3, 0, 0))
        mobs.spawn(value, positions.create(3, 0, 0))
    }
})
```

### Try the *"zoo"* command

Go back into your Minecraft world, and type the command "zoo" into the chat window, and watch the animals appear!

![Zoo](/static/courses/csintro/arrays/zoo.jpg)

## Complete Zoo Program

```blocks
let animalarray: number[] = []
player.onChat("pen", function () {
    builder.teleportTo(positions.create(5, 0, -5))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(SixDirection.Forward, 10)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(blocks.block(Block.OakFence))
})
player.onChat("zoo", function () {
    for (let value of animalarray) {
        mobs.spawn(value, positions.create(3, 0, 0))
        mobs.spawn(value, positions.create(3, 0, 0))
    }
})
animalarray = [mobs.animal(AnimalMob.Pig), mobs.animal(AnimalMob.Rabbit), mobs.animal(AnimalMob.Ocelot),mobs.animal(AnimalMob.Horse), mobs.animal(AnimalMob.Donkey), mobs.animal(AnimalMob.Mule), mobs.animal(AnimalMob.Llama), mobs.animal(AnimalMob.PolarBear)]
```

**Shared Program:** https://makecode.com/_2Jc55Xbjz1v8

## Challenges

## Challenge 1 - Add more animals to the zoo

Create a larger pen and add all the different types of animals! There are 19 different kinds. Then, watch the craziness ensue!

![Zoo - Challenge 1](/static/courses/csintro/arrays/zooch1.jpg)

### Challenge 2 - Create a second array for animal names

This challenge applies several concepts in one. Are you up for it? Remember that learning is not always about winning. If you struggle with this challenge then don't feel discouraged. If you find this challenge too easy then perhaps you could make your own challenge and share it with another student!?

An ocelot is a very obscure animal to many so it would be nice to know the names of the animals we are spawning.

Create a second array that lists the names of the animals from `||variables:animalarray||`. Then as the animals spawn use `||player:say||` to give feedback. Including a `||loops:pause||` between animals will give the user more time to read and understand what the different animals are.

Tasks:

1. Create an `||variables:animalnames||` array.
2. Put all the animal names into `||variables:animalarray||`.
3. Print out the names after they spawn.
4. Pause the code after printing for 1 second or more... your choice on how long to pause.

Because there are so many animals to list for task #2, you may consider doing some of this in javascript instead of using blocks. After you create an array you can enter the names of the animals much easier in javascript. Plus you can see all the names much easier.

Block coding is awesome but in this case, typing in javascript would be much faster. Look at the example below. Can you figure out how to copy this format for all the animals? Then when you finish you can add your `||player:say||` and `||loops:pause||` by going back into the block editor.

Make sure your commas and quotation marks are all in the right place or you will get an error.

![Use Javascript for Speed](/static/courses/csintro/arrays/challenge-2-use-javascript.png)

### (Tasks 1-2)

The blocks below are the answers and might help you get the job done faster. Now you just need to figure out where to place them! In order to print the name of the animals you need to use a counter that acts as the key to each name. Remember the key is the number where things are put in the array.... for our new array, the keys will look like:

Chicken = 0  
Cow = 1  
Pig = 2  
etc...

You will need to set the names for each animal in our new array. One example is given below. Now you just need to figure out where to place this code and finish setting the names for all the animals.

```block
let animalnames: string[] = []
animalnames[0] = "Chicken"
```

### (Tasks 3-4)

Below you have been given the counter 'CurrentAnimalNum'. This acts as the key when getting values from the `||variables:animalnames||` array.

If you don't understand all of this, it is not the end of the world. Just see if you can place this code in the right place. As you do this, try and understand why things are happening the way they are. If you need help on placement, ask your instructor for guidance.

## Where would you place these blocks in our existing code?

## Helper Blocks

```block
let currentAnimalNum = 0
let animalnames: string[] = []
animalnames = ["Dog", "Cat"]
player.say(animalnames[currentAnimalNum])
currentAnimalNum += 1
loops.pause(1000)
```

![Zoo - Challenge 2](/static/courses/csintro/arrays/zooch2.jpg)

## Experiments

Let's add to our existing zoo to continue to make it bigger and better. Play around with this code and see what else you can add to make the zoo more complete!

### Experiment 1 - Add a birdhouse, birds only!

In this experiment, we separate the birds into their own array and build a cage for them specifically. An aviary is a building where birds are kept. This is what they will get. Type 'zoo' into the chat window and now you will get your land animals in their pen and birds in their own aviary. However, there are still some problems.

How might you make this better? Can you build a separate pen for each animal? What else can you think up to do?

![Aviary](/static/courses/csintro/arrays/exp1-1.jpg)

Here you can see one problem. Look how the donkey is red. This is because our wolves are attacking them. Perhaps wolves need to be separated into their own pen or cave or something. ![Growing Zoo](/static/courses/csintro/arrays/exp1-2.jpg)

### Experiment 2 - Add another zoo exhibit for the squids

Since squids swim in water, this script builds a place for them to swim in the ground and then fills the ground with the water. Type 'zoo' in the chat window to get started.

Again, you might try to extend the zoo even more by adding signs, different features, caves, rivers, or any other thing you can think of.

Notice the code uses functions to help organize the new enclosures for different kinds of animals. Each function creates the pen and animals for each type of animal.

![Squids from a Boat](/static/courses/csintro/arrays/aquariumsquid.jpg)

![Squids Upclose](/static/courses/csintro/arrays/exp2-2.jpg)

![Squid Enclosure and Our Whole Zoo](/static/courses/csintro/arrays/exp2-1.jpg)