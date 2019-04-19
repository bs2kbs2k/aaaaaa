# Activity: Fall Is in the Air

Minecraft Survival worlds are full of high places. Let’s use an *event handler* and a *counter* to come up with a useful postmortem report after you have fallen from a high place. This death report will show how many blocks you fell before respawning.

For this project, you will want to be in a Survival world next to a large cliff. Alternatively, you can toggle between Creative mode and Survival mode and fly up to a high point for testing.

You will create a variable that keeps track of the distance you have fallen, and you will report that distance in blocks after you respawn.

## Do the activity

### Pull out chat commands and player events

1. Create a new MakeCode project and name it "Falling."

2. From `||player:PLAYER||`, drag a `||player:on chat command||` to the Workspace.

3. Right-click the `||player:on chat command||` and select `duplicate`. Do this twice so that you end up with three `||player:on chat command||` blocks.

4. Name these commands `"cr"` (creative), `"su"` (survival), and `"pm"` (postmortem).

5. From `||player:PLAYER||`, drag out two event blocks: `|player:on player walk||`, and `|player:on player died||`.

6. Change `||player:on player walk||` to`||player:on player fall||`.

```blocks
player.onChat("cr", function () {

})
player.onChat("su", function () {

})
player.onTravelled(TravelMethod.Walk, function () {

})
player.onChat("pm", function () {

})
player.onDied(function () {

})
```

### Be "Creative"

The first thing you’ll do is construct the `||player:on chat command||` for `"cr"`. This command will change the game mode to Creative. You can fly in Creative mode, so this is very helpful to get to a high place.

1. From `||gameplay:GAMEPLAY||`, drag out `|gameplay:change game mode||` and drop it inside `||player:on chat command "cr"||`.

2. In `||gameplay:change game mode||`, select `creative` mode, and change `||mobs:target||` to `yourself @s`.

```blocks
player.onChat("cr", function () {
    gameplay.setGameMode(
    GameMode.Creative,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
```

Now, to switch to Creative mode, all you need to do is issue the chat command **"cr"** in the chat window and you will be able to double-tap the spacebar to fly straight up as high as you want.

### Just survive

You’ll want to use the same strategy to switch into Survival mode.

1. From `||gameplay:GAMEPLAY||`, drag out `|gameplay:change game mode||` and drop it inside `||player:on chat command "su"||`.

2. In `||gameplay:change game mode||`, change `||mobs:target||` to `yourself @s`.

```blocks
player.onChat("su", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
```

### Make the `fall` variable

1. In `||variables:VARIABLES||`, click **Make a Variable**, and name the new variable `||variables:fall||`.

This variable will start incrementing (adding up) each block the player falls. You will also use another variable to store the final number of blocks the player fell.

### Remember the fall

1. In `||variables:VARIABLES||`, click **Make a Variable**, and name the new variable `||variables:report||`.

2. From `||variables:VARIABLES||`, drag `||variables:change item||` into the `||player:on player fall||` event.

3. In `||variables:change item||`, select your variable `fall` instead of the default, `item`.

4. From `||variables:VARIABLES||`, drag out `||variables:set item||`. Right-click and duplicate this once. Now you should have two.

5. Put one `||variables:set item||` into `||player:on player died||`.

6. In this `||variables:set item||` block, select `report` instead of `item`.

7. From `||variables:VARIABLES||`, drag `fall` into the second slot and replace the `0` so the block reads `set report to fall`.

This will save the value of the latest fall in the `report` variable. Then you can reset fall to 0 and try another jump.

Basically, something like this is happening after you fall 42 blocks:

1. You fall 42 blocks.
2. The variable `fall` equals 42.
3. You copy 42 to `report`.
4. You change `fall` back to 0.
5. You print out the report because you are curious.
6. You go find something else to jump off of.

### Reset the fall count

1. Move the other `||variables:set item||` you duplicated in step 15. Put this inside `||player:on player died||` at the very bottom. Change the variable to `fall`.

```blocks
let fall = 0
let report = 0
player.onDied(function () {
    report = fall
    fall = 0
})
player.onTravelled(TravelMethod.Fall, function () {
    fall += 1
})
```

### Report your fall count

Finally, you need to report the height of your fall.

1. From `||player:PLAYER||`, drag `||player:say||` into `||player:on chat command "pm"||`.

2. Click **Advanced** to see the `||text:TEXT||` Toolbox category.

3. From `||text:TEXT||`, drag `||text:join||` into `||player:say||` and replace `"Hi!"`.

```blocks
let report = 0
player.onChat("pm", function () {
    player.say("Hello" + "World")
})
```

### Join the variable to the message

1. In `||text:join||`, enter **"You fell "** in the first slot, replacing `"Hello"`.

2. From `||variables:VARIABLES||`, drag `||variables:report||` into the second `||text:join||` slot, replacing `"World"`.

```blocks
let report = 0
player.onChat("pm", function () {
    player.say("You fell " + report)
})
```

### More fall details

This will work, but it will look something like "You fell 43". Well, 43 what? You should tell the player how many units they fell. In this case, you want to say "You fell 43 blocks". In order to do this, you will need to go into JavaScript.

1. Click the **JavaScript** toggle button at the top of the screen to switch into the MakeCode JavaScript editor.

### ~ hint

All the block coding you have tried thus far is also viewable in this raw form. Don't get intimidated - just take a look, and try to read it as you would read sentences. By looking back and forth between Blocks and JavaScript, you can probably see what it is doing pretty well!

### ~

1. Find this line of code: `player.say("You fell " + report)`.

2. Add the string `" blocks"` to the end of the line so it looks like this:

```typescript-ignore
player.say("You fell " + report + " blocks")
```

### Go back to Blocks

1. Click the **Blocks** toggle button at the top of the screen to switch back into the MakeCode Blocks editor.

Do you see how the block changed? Are you daring enough to try and change more things on the JavaScript side? See what happens!

### Try out the commands

That’s it! Now enter **"cr"** in the chat window to enter Creative mode, double-tap the spacebar, hold it down until you are high in the sky, and then enter **"su"** in the chat window to fall back to earth. After you die, click **Respawn**. In the chat window, enter **"pm"**. You can see a report of how many blocks you fell!

![you fell 73 blocks](/static/courses/csintro/variables/you-fell-73-blocks.png)

### Complete program

```blocks
let fall = 0
let report = 0
player.onChat("cr", function () {
    gameplay.setGameMode(
    GameMode.Creative,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onChat("su", function () {
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onDied(function () {
    report = fall
    fall = 0
})
player.onTravelled(TravelMethod.Fall, function () {
    fall += 1
})
player.onChat("pm", function () {
    player.say("You fell " + report + " blocks")
})
```

**Shared Program:** https://makecode.com/_MoyCau9H9VvP

## Challenges

Now you can change some things to make your own different and unique situations!

### Challenge 1 - Let's Report in Blocks

Can you figure out a way to print your fall report in blocks in the Minecraft world? Do you think this might be easier to read than the small words in the chat window?

This is what you will need to do:

* Change the `say` block to something else. Can you figure out what block will allow you to print this information in blocks?

### Challenge 2 - Set Up a Variable to Track Total Fall Distance over Multiple Falls

So far, you can report your last fall, but what about reporting the total number of blocks you fall over several jumps? If you fall 40 blocks and then 50 blocks, the total is 90 blocks. Entering **"pm"** would return, "You fell 50 blocks". Your new command, "tot" (total) will actually say, "You have fallen 90 blocks total so far! Keep Jumping!".

This is what you will need to do:

1. You need a new `||variables:VARIABLE||` in which to store the total fall distance.
2. You need to use `||variables:set||` to add `fall` to this variable every time you die.
3. You need a new `||player:on chat command||`. You can use "tot" or something else - it doesn't really matter what you call it.
4. You need to use `||text:join||` to put the enture message together like you did before.

![swim counter](/static/courses/csintro/variables/total-distance-fell.jpg)

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Track Swim Distance

What if you report how far you swim? You could report other actions you might do as well. You could keep track of several actions and then total them all together, or provide a massive report showing all the things you did. Play around with the code and see what kinds of things you might report and store in variables.