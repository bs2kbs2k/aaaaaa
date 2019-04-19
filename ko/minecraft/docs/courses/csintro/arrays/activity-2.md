# Activity: Warp Belt

One of the most enjoyable activities when playing Minecraft is to build houses. Often, these houses are spread all over the world. Sometimes while exploring, you might discover awesome hidden temples or villages in remote locations. It can be challenging to remember how to get back to all of those places. In this activity, you'll see how to create a tool that you can use to teleport between all of those different locations. This 'Warp Belt' will save the locations in memory by using arrays so you can easily jump between them all.

### ~ hint

In the chat window, enter '/locate' followed by a space.

You can then enter in any structure you might want to find in the world you are in. You might use this to first locate things, teleport there, and then save the locations in your warp belt!

For example, to find a mansion in a world, enter the following:

    /locate mansion
    

![Locate](/static/courses/csintro/arrays/tip-locate.jpg)

### ~

You'll support four main commands in this program:

* **Delete**: This creates an empty array, effectively deleting your old one.
* **Save**: This saves your current position to the next empty spot in the array.
* **Warp**: This command, when entered with a number, teleports the player to the position stored at that index in the array.
* **List**: This command prints all the positions in the array, with their index numbers.

## Do the activity

### Create an empty array

1. Create a new MakeCode project called **Warp**.

2. From `||loops:LOOPS||`, drag a `||loops:on start||` block onto the coding Workspace.

3. Open `||variables:VARIABLES||` and **Make a Variable**.

4. Name this variable `warp_array`, and click **Ok**.

5. From `||variables:VARIABLES||`, drag a `||variables:set||` into the `||loops:on start||`.

6. From the `||variables:set||` drop-down menu, select the `warp_array` variable.

Now let's set `||variables:warp_array||` to a new array.

1. Click the Advanced tab in the Toolbox to display `||arrays:ARRAYS||`.

2. From `||arrays:ARRAYS||`, drag `||arrays:create array with||` into the `||variables:set "warp_array" to||`.

3. In `||arrays:create array with||`, click the minus sign **(–)** to empty it. You should see the title change to `||arrays:create empty array||`.

```blocks
let warp_array: number[] = []
warp_array = []
```

### Make the *"delete"* command

Now, let's create a command to delete our array. When you "delete" the array, you simply want to set it to an empty array so you are deleting the array's contents.

1. From `||player:PLAYER||`, drag an `||player:on chat command||` onto the Workspace.

2. Name this command **delete**.

3. Right-click the existing `||variables:set||` in `||loops:on start||` and select Duplicate.

4. Drag this new `||variables:set||` block into `||player:on chat command "delete"||`.

5. From `||player:PLAYER||`, drag a `||player:say||` after `||variables:set||`.

6. In `||player:say||`, enter a message, for example, `"Array deleted"`.

```blocks
let warp_array: number[] = []
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
warp_array = []
```

### Make the *"save"* command

To save locations into our array, you will want the save command to add the current position to the end of our array when we call it.

1. From `||player:PLAYER||`, drag another `||player:on chat command||` to the Workspace.

2. Name this command **save**.

3. From `||arrays:ARRAYS||`, drag `||arrays:add value to end||` into `||player:on chat command "save"||`.

![Grab the 'add value at end' block](/static/courses/csintro/arrays/add-value-end.jpg)

### Set the position into the warp array

1. From the `||arrays:add value to end||` drop-down menu, select `warp_array` as the array you want to add values to.

You are saving positions, so you need to adjust `||arrays:add value to end||` a little more.

1. From `||player:PLAYER||`, drag a `||player:player world position||` into the Add value of `||arrays:add value to end||`.

```blocks
let warp_array: Position[] = []
warp_array.push(player.position())

```

1. From `||player:PLAYER||`, drag a `||player:say||` block after the `||arrays:"warp_array" add value "player world position" to end||` block.

2. In the `||player:say||` block, enter a message, for example, `"position added"`.

```blocks
let warp_array: Position[] = [] 
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
player.onChat("save", function () {
    warp_array.push(player.position())
    player.say("position added")
})
warp_array = []
```

### Create a *"warp"* command

The player will use the warp command by passing in a number, such as "warp 1" or "warp 2", to teleport themselves to a saved location in the array.

1. From `||player:PLAYER||`, drag a `||player:on chat command||` to the Workspace.

2. Name this command **warp**.

3. In `||player:on chat command "warp"||`, click the plus sign **(+)** to add a parameter. It is called `num1` by default. This is a variable. This is the number of the location you want to warp to. Recall that in arrays, the number where something is stored is called the *index* or *key*. You will pass in the index here through `||player:on chat command "warp"||`. Then you will get the information stored in that location.

Therefore, if you wanted to warp to our third saved location, you would enter **warp 3** in the chat window. The computer goes to the third location and gets your coordinates for you!

1. You should always name variables something meaningful. Rename `num1` to `Warp_LocationNum`.

2. From `||player:PLAYER||`, drag `||player:teleport to||` into `||player:on chat command "warp"||`.

Now we just need to get the information stored in our array.

1. From `||arrays:ARRAYS||`, drag `||arrays:get value at||` into `||player:teleport to||` and replace the existing coordinates block.

```blocks
let warp_array: Position[] = []
player.teleport(warp_array[0])

```

1. From the `||arrays:get value at||` drop-down menu, select the `warp_array` variable.

2. From the `||variables:VARIABLES||`, drag `Warp_LocationNum` into the second slot of the `||arrays:get value at||`.

```blocks
let warp_array: Position[] = []
player.onChat("warp", function (Warp_LocationNum) {
    player.teleport(warp_array[Warp_LocationNum])
})
```

Now, when you call the warp command with a number, the code will grab the position in the spot you specify. Then you will teleport to the position stored in the array.

### Additional improvements

There are a couple of ways you can improve this warp command. Some of these improvements will be challenges you will need to complete. However, before you get to the challenges, try to do one more thing:

### ~ hint

Remember that the first item in an array always has an index of 0. This means to get the first saved thing in an array, you need to use 0. It seems a little strange to enter "warp 0" to get to the first position in your array. Let's adjust this so that the player can enter the number of the warp starting with 1. To do this, all you need to do is subtract one from `Warp_LocationNum` to get the right index. You'll do this in the MakeCode JavaScript editor.

### ~

1. Click the **JavaScript** tab at the top of the screen to see your program in the JavaScript editor.

![Click the JavaScript tab](/static/courses/csintro/arrays/javascript-tab.jpg)

1. Find the `player.onChat("warp" ...` function.

2. In the following line of code, subtract `1` from the index by changing to:

>     player.teleport (warp_array [Warp_LocationNum - 1])

The function now looks like this:

```typescript-ignore
player.onChat("warp", function (Warp_LocationNum) {
    player.teleport(warp_array[Warp_LocationNum - 1])
})
```

1. Click the **Blocks** button at the top of the screen to go back to the Block editor.

You will see that the block editor chose the proper blocks for you. Yes, you could have done this in blocks, but it is good to get used to seeing pure code and not being scared of it.

### Completed Code

```blocks
let warp_array: Position[] = []
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
player.onChat("save", function () {
    warp_array.push(player.position())
    player.say("position added")
})
player.onChat("warp", function (Warp_LocationNum) {
    player.teleport(warp_array[Warp_LocationNum - 1])
})
warp_array = []

```

![Activity 2 - Final Result](/static/courses/csintro/arrays/act2-final.jpg)

## Challenges

Let's continue to improve our warp belt code by checking what the user enters and giving them feedback.

### Challenge 1 - Make Sure a Valid Jump Spot Was Entered

There is one more improvement you can do to make your program more user-friendly. If the player enters a number that is larger than the last index in the array, there should be some sort of a warning. Otherwise, it's odd to enter a command and have nothing happen. It is good programming practice to give feedback to the user for bad input or other errors.

You will need to do the following:

1. Add an if statement to check what was entered.
2. Check to see if value is bigger than size of `warp_array`.
3. If bigger, give a warning message like "Sorry, no such location".
4. If the same or smaller than size of `warp_array`, you will teleport the player.

You will need to set up your if statement and find a way to get the size or length of `warp_array`.

### Challenge 2 - Print All Saved Warp Coordinates

You need to print the list of all saved warp coordinates in a world.

To do this, you can use a special loop.

```blocks
let warp_array: Position[] = []
for (let value of warp_array) {

}
```

There are several ways to do this. You could make a `||function:function||` to handle this and call the function after each save. You could use an `||player:on chat command||`.

The basics are to loop through `||variables:warp_array||` and print its contents. Again, with printing you have options. You could use `||player:say||` blocks to display the contents in the chat window, or you might write the results in the sky with blocks by using the `||blocks:print||` block.

The solution given uses a function. The function is called after every save.

## Experiments

Here, there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1

Enter `save` in your chat window, and then press enter. You should see directions prompting you to enter a number now. You will now save coordinates and keep a name of the type of location connected to this.

Enter `list` to list all the locations you have saved.

This code does a few things. First, it uses multiple arrays that have connected information. This means the same index works with multiple arrays and the information you get is connected. In one array, the coordinates are stored; in another, the names of the locations. A third array is used to keep the default locations, but it is not necessary to do it this way.

What places does it save?

### ~ hint

In the chat window, enter '/locate' followed by a space.

You can then enter in any structure you might want to find in the world you are in. You might use this to first locate things, teleport there, and then save the locations in your warp belt!

For example, to find a mansion in a world, enter:

    /locate mansion
    

![Locate](/static/courses/csintro/arrays/tip-locate.jpg)

### ~

What other things could you do with teleporting or coordinates in code? Can you use arrays creatively to make the code more complex?

What about saving a monster type to each location? Then when you warp back, it spawns that monster! You could make a teleporting game with missions to teleport to different locations, kill all the monsters there (which you spawn with code), and then teleport to the next location.