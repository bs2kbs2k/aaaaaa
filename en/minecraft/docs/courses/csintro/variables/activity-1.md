# Activity: Chicken Storm

In this activity, students use a variable to determine the number of chickens to spawn in Minecraft, and they’ll make these chickens fall from the sky like a storm of chickens!

## Do the activity

### Make a new project

1. Create a new MakeCode project and name it "Chicken Storm."

2. From `||player:PLAYER||`, drag `||player:on chat command||` into the coding Workspace and change the command to `"chickens"`.

3. From `|loops:LOOPS||`, add a `||loops:repeat||` loop inside `||player:on chat command "chickens"||`.

4. Open `||mobs:MOBS||`, and add a `||mobs:spawn animal||` block inside the `||loops:repeat||` loop.

5. Change the **Y** coordinate to `10` inside `||mobs:spawn animal||`. Chickens will spawn 10 blocks above your head.

```blocks
player.onChat("chickens", function () {
    for (let i = 0; i < 4; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```

1. Go into Minecraft, press `T` to open the chat window, and enter **chickens** in the chat window. It's raining hens!

### We want more chickens!

You want more chickens, of course, and you want to use a variable that will allow you to easily change the number of chickens.

You can provide the number of chickens when you call the `||player:on chat command||`.

1. Click the plus sign **(+)** just to the right of the `||player:on chat command||` for `"chickens"`. Another drop-down menu should appear, with the name `num1` at the top of it. `num1` is a number variable that you can use in your code.

### ~ hint

It is good coding practice to give variables meaningful names. `num1` is the default name, but it means nothing. It would be better to name this variable something else so you can recognize it. In a large program, naming variables with names you can identify makes finding problems much easier. Challenge 1 of this lesson covers this topic.

### ~

1. From `||variables:VARIABLES||`, replace the number `4` in `||loops:repeat||` with `||variables:num1||`.

![variables drawer](/static/courses/csintro/variables/variables-drawer.jpg)

```blocks
player.onChat("chickens", function (num1) {
    for (let i = 0; i < num1; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```

Now if you enter **chickens 15** in the chat window, the variable `num1` will take the value `15`. You have stored the value **15** inside `num1`. If you enter **chickens 25**, `num1` takes the value **25**.

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Rename num1 to Something More Meaningful

Let's change the code so that you are not using `num1`. The name `num1` does not represent anything meaningful and could be hard to understand in a big block of code. Instead, your new variable will be called `ChickenNum` because the number you store is the number of chickens.

To do this, you will need to...

1. Make a new `||variables:VARIABLE||`.

2. Rename it `ChickenNum`.

3. Replace `num1` in your code with `ChickenNum`.

When you are done, everything should work the same as before, but now you can read your code a little more easily.

### ~ hint

Remember that the search is your friend. Use your instincts, decide what you want to accomplish, and search for those things. See what you find!

### ~

### Challenge 2 - Give Feedback

Let's have your chicken rain machine speak back to you. This will be kind of like ordering at a drive-through window. Right before chickens start falling, have your code say "`ChickenNum` chickens! Coming right up!"

So if you entered **chickens 5** in the chat window, the response would be, "5 chickens! Coming right up!". Then five chickens would fall from the sky on your head.

To do this, you will need to...

1. Figure out how to "say" things in the chat window.

2. Use the `join` block to put together `ChickenNum` + " chickens! Coming right up!"

3. Put this new block in the right location in your code. If you put it in the wrong spot, the chat window will respond many times.

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Default Chicken Value

Now that you have created a chicken command that takes a number variable and produces that many chickens, it is good programming practice to make sure to handle cases where the **chickens** command in the chat window isn't given a number. By default, `ChickenNum` has a value of 0. If you type the **chickens** command but forget to type a number after it, you will at least get a couple of chickens, which isn’t as good as 10 chickens, but it’s better than no chickens at all!

How can you change this code? Maybe you do something interesting if the user types a certain number. For example, if the user types **20** in the chat window (`chickens 20`), what if raw chickens fell from the sky instead? Could you make a normal chicken fall, then a cooked chicken, then a normal chicken, and so on?

### Experiment 2 - Chicken Storm

You can further improve the realism of the **chickens** command by using the `||positions:pick random position||` block from the `||positions:POSITIONS||` Toolbox drawer. This block will scatter the chickens randomly around the area described by the two coordinates. You can also vary the height of the drop, so that the chickens will land at different times. Now it is truly a storm of chickens!

Try this out with other animals or objects.