# Activity: Arrow Counter

You can use variables to count the number of times something happens in your world. You can use them to keep score, or you can use a conditional statement to cause something to happen when the counter gets to a certain number. Conditional statements are covered in more detail in Lesson 6.

Let’s look at an example that uses a counter to keep track of the number of arrows you shoot.

## Do the activity

### Make a new project

1. Create a new MakeCode project and name it "Arrow Counter."

2. In `||variables:VARIABLES||`, click the **Make a Variable** button.

3. Name the new variable `arrows`.

![make variable button](/static/courses/csintro/coordinates/make-variable-button.png)

![Name a new variable](/static/courses/csintro/variables/make-variable-arrows.jpg)

Now this new `arrows` variable will be available to you in the drop-down menus of many of the blocks that use variables.

### Record arrows shot

1. From `||player:PLAYER||`, drag `||player:on arrow shot||` into the Workspace.

2. From `||variables:VARIABLES||`, drag `||variables:change item||` inside `||player:on arrow shot||`.

3. In `||variables:change item||`, select `||variables:arrows||`.

![Select the variable 'arrows'](/static/courses/csintro/variables/select-variable-arrows.jpg)

Now, every time you shoot an arrow, the counter or variable you called `arrows` will increase by one. (If you want to decrease the value of a variable, use a negative number.)

### Make an arrow message

Let’s create a way to actually see the value of the variable. The `||player:say||` block prints a line of text to the chat window at the top of the Minecraft game screen.

1. From `||player:PLAYER||`, add a `||player:say||` block under `||variables:change arrows||`.

### Put text together

Let’s join the number variable `arrows` with some text so you can get a message you can read and understand.

1. Click the **Advanced** category in the Toolbox to display the `||text:TEXT||` Toolbox drawer.

![make variable button](/static/courses/csintro/variables/advanced-text.png)

1. From `||text:TEXT||`, drag `||text:join||` into `||player:say||` to replace the `"Hi"` string.

```blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("Hello" + "World")
})
```

### ~ hint

Variables that hold text like `"Hi!"` are called *string variables*.

### ~

### Join the variable to the message

1. In the first slot of `||text:join||`, enter `"Arrows Shot: "`.

2. From `||variables:VARIABLES||`, drag the `arrows` variable into the second slot of `||text:join||`, replacing the string `"World"`.

This block will join the string `"Arrows Shot: "` to the number variable. `||player:say||` will print the message at the top of the screen every time you shoot an arrow.

```blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("Arrows Shot: " + arrows)
})
```

**Shared Program:** https://makecode.com/_1DPAgv2iX9s4

Go into Minecraft and try it out! You can give yourself a bow and arrows by typing the following commands into the chat window:

    /give @p bow
    /give @p arrows 64
    

To fire your arrows, hold down the right mouse button to draw the bow.

### ~ hint

You can type `"/give @p"` to give your player all kinds of different items.

![give player command](/static/courses/csintro/variables/give-player-command.jpg)

For example, to give your player 64 beacons, type: `"/give @p beacon 64"`

![give player command full example](/static/courses/csintro/variables/give-player-command-full-example.png)

### ~

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Modify the Message and Track 10 Arrows

The player only gets 10 shots from now on. You want the message to display the number of shots the player has left out of 10. Can you modify the message and variable to do this?

To do this you will need to...

1. Change the text message so it is appropriate for the new situation.

2. Set `||variables:arrows||` equal to 10 when your code starts.

3. Change `||variables:arrows||` so it subtracts when arrows are shot.

### Challenge 2 - Provide a Message When a Player Runs Out of Arrows

Set up this **if** conditional somewhere in your code to display a message or make something happen when the player runs out of arrows.

```block
let arrows = 0
if (arrows == 0) {

}
```

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - A Full Target Practice Experience

It would be nice to set up a full experience so the player can practice shooting. In this experiment you spawn some rabbits, arm your player with a bow and some arrows, and set the mode to Survival. You will also track the shots your player takes.

What things could you change or add to make this experience more interesting?

### Experiment 2 - A Counter to Track the Number of Rabbits Hit

It might be nice to have a counter to track the number of rabbits you hit. You will use the `on mob killed` block and change the `animal` mob to `rabbit`. This uses the same logic as the arrow counter.

Could you make a total misses counter? How else might you modify this code to make it the ultimate target practice experience?