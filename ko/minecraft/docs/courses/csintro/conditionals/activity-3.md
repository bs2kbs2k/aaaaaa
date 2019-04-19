# Activity: All Mine!

In addition to chopping trees for wood, you will probably want to mine the earth for precious minerals. One good strategy for finding the rarest of minerals, diamond, is to tunnel deep beneath the earth to levels Y12 or Y13, and then create a series of branching tunnels off a central passageway. If you completed the previous [Lesson 5: Iteration - Independent Staircase Project](/courses/csintro/iteration/project), you may have some code that gets the agent to dig it for you. If not, get yourself down to Y12 or Y13, and we’ll meet you there!

## ~ hint

**Getting down there!**

Find your world position in the game (press the `F1` key to see your world position on the screen), and then enter the command: `/tp X 12 Z`, where X and Z are your current world coordinates. This will teleport you directly down to level 12 altitude in your Minecraft world. Make sure you equip yourself with a pickaxe and torches to make some room and to see down there!

## ~

In this activity, you’ll create a basic mining agent that automatically destroys blocks in front of it and collects everything. You’ll use conditional statements to test for precious minerals. The agent is one block tall, so you’ll send it forward 64 blocks, and then have it turn around, move up one block, and come back. If the agent finds anything of value, it will let you know and collect the ore.

## Do the activity

### Create controls for the agent

1. Create a new MakeCode project and name it **All Mine**.

2. Rename the existing `||player:on chat command||` to `"do"`.

Because you are always doing things with your agent, you should make it easy to command it. You can do this with a `||logic:if then else||` statement. You can make a simple menu to handle all the agent commands.

1. Drag a `||logic:if then else||` into `||player:on chat command "do"||`. Click the **(+)**  
    sign on the `||logic:if then else||` to add a third branch for this because you will test for three conditions.

2. Click the **(+)** sign on `||player:on chat command "do"||` and rename `num1` to **AgentOrder**.

```blocks
player.onChat("do", function (AgentOrder) {
    if (true) {

    } else if (false) {

    } else {

    }
})
```

Now just test to see what the user entered. You want the user to be able to teleport the agent and turn it. The third branch will give the user some information if nothing is entered.

1. From `||logic:LOGIC||`, grab the '0 = 0' comparison block and duplicate this because you need two.

2. Place these into the `||logic:if then else||`.

3. Adjust these so you test for what the user entered. We need to test the value of `||variables:AgentOrder||`. Let's say a value of `1` means the agent teleports and a value of `2` means the agent should turn.

```blocks
player.onChat("do", function (AgentOrder) {
    if (AgentOrder == 1) {

    } else if (AgentOrder == 2) {

    } else {

    }
})
```

Last, you just need to add blocks to the branches to make your agent do the actions.

1. From `||agent:AGENT||`, add `||agent:agent teleport to player||` into the first branch of your `||logic:if then else||`.

2. From `||agent:AGENT||`, add `||agent:agent turn||` into the second branch of your `||logic:if then else||`.

3. In the last branch, add a message to give the user directions. From `||player:PLAYER||`, add a `||player:say||` to the third branch of your `||logic:if then else||`.

4. Adjust the text in the `||player:say||` to read **Enter 1 to teleport or 2 to turn**.

```blocks
player.onChat("do", function (AgentOrder) {
    if (AgentOrder == 1) {
        agent.teleportToPlayer()
    } else if (AgentOrder == 2) {
        agent.turn(TurnDirection.Left)
    } else {
        player.say("Enter 1 to teleport or 2 to turn")
    }
})
```

There, now controlling the agent is a lot easier.

### ~ hint

You can expand this code (Agent Controls) and just copy and paste it into anything that requires the agent. This would be a quick way to get a jump start on projects.

### ~

### Make the *"dig"* command

1. From `||player:PLAYER||`, place a `||player:on chat command||` into the coding Workspace, and rename it to `"dig"`.

You can only mine diamonds in **Survival** mode, so the first thing you should do is make sure you change the game mode to Survival.

1. From `||gameplay:GAMEPLAY||`, place `||gameplay:change game mode||` into `||player:on chat command "dig"||`.

2. Adjust `||gameplay:change game mode||` by clicking the player selector drop-down menu to select `yourself @s`.

![Set survival mode for yourself](/static/courses/csintro/conditionals/pick-yourself.jpg)

From `||logic:LOGIC||`, drag a `|logic:if then else||` out and drop it after the `||gameplay:change game mode||` block.

```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    if (true) {
    } else {
    }
})
```

### Look for diamonds

You want to give an alert if the agent finds valuable blocks like diamond ore.

1. From `||logic:LOGIC||`, grab an Equals (=) comparison block to replace the `true` in your `|logic:if then else||`.

2. From `||agent:AGENT||`, drag `||agent:inspect||` into the first slot of the Equals, `||logic:0 = 0||`, replacing the number `0`. The `||agent:inspect||` block will check the block directly in front of the agent.

3. From `||blocks:BLOCKS||`, drag a `||blocks:block||` out and drop it into the second slot of the Equals, `||logic:0 = 0||`.

4. In `||blocks:block||`, use the drop-down menu to select `Diamond Ore` as the block you are checking. (You can also use the Search bar to find it.)

![Select diamond ore](/static/courses/csintro/conditionals/select-diamond-ore.jpg)

```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.DiamondOre)) {

    } else {

    }
})
```

### Get rich!

If you do find Diamond Ore, then you'll want to print a message to the screen and mine the ore.

1. From `||player:PLAYER||`, drag `||player:say||` and drop it into the first branch of the `|logic:if then else||`.

2. In the `||player:say||` block, enter a message like `"We’re rich!"`.

3. From `||agent:AGENT||`, drag the following three blocks and drop them in order under the `||player:say||` block: `||agent:agent destroy||`, `||agent:agent move||`, and `||agent:agent collect all||`.

```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.DiamondOre)) {
        player.say("We're rich!")
        agent.destroy(SixDirection.Forward)
        agent.move(SixDirection.Forward, 1)
        agent.collectAll()
    } else {
    }
})
```

### Destroy the other blocks and keep mining

If the agent doesn’t find Diamond Ore, he should simply destroy the non-valuable block in front of it, and move forward without collecting anything.

1. From `||agent:AGENT||`, drag `||agent:agent destroy||` and `||agent:agent move||` into the `||logic:else||` clause.

2. You need to repeat this process 64 times, so you'll use a loop. From `||loops:LOOPS||`, drag a `||loops:repeat||` loop out and surround your `||logic:if then else||` block.

3. In the `||loops:repeat||` loop, enter the number **64**.

```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    for (let i = 0; i < 64; i++) {
        if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.DiamondOre)) {
            player.say("We’re rich!")
            agent.destroy(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
            agent.collectAll()
        } else {
            agent.destroy(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        }
    }
})
```

### Make a return trip

This will send your agent forward to mine 64 blocks, but you need to have it turn around and come back. So, you’ll use another loop outside your `||loops:repeat||` loop. You are creating a "Nested Loop" because there will be a loop within a loop.

1. From `||loops:LOOPS||`, drag another `||loops:repeat||` loop out and surround your existing `||loops:repeat 64||` loop.

2. In the `||loops:repeat||` loop, enter the number **2**, because you’ll want your agent to mine just two rows of blocks. At the end of the first row, you want your agent to move up and turn around.

3. From `||agent:AGENT||`, drag the following four blocks out and drop them in order under the inner `||loops:repeat||` loop: `||agent:agent destroy||`, `||agent:agent move||`, and two `||agent:agent turn||` blocks. You place them here to position your agent to come back. You will need to adjust the direction for a few of these blocks by using the the drop-down menu to select `up`.

### ~ hint

**Getting down there!**

Remember that you will first need to teleport your character down to where you can mine.

Find your world position in the game (press the F1 key to see your world position on the screen), and then enter the command: `/tp X 12 Z` where **X** and **Z** are your current world coordinates. This will teleport you directly down to level 12 altitude in your Minecraft world. Make sure you equip yourself with a pickaxe and torches to make some room and to see down there!

### ~

### Complete program

```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 64; i++) {
            if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.DiamondOre) || agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.GoldOre)) {
                player.say("We're rich!")
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
                agent.collectAll()
            } else {
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
            }
        }
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
        agent.turn(TurnDirection.Left)
        agent.turn(TurnDirection.Left)
    }
})
```

### ~ hint

**Lots that could go wrong!**

Several factors are at play when mining deep under the earth! You might teleport down and find something unexpected.

![LAVA](/static/courses/csintro/conditionals/act3-lava.jpg)

The agent might not respond the way you initially think it should. The agent will not dig unless it is near your character when the command is issued, so you might get a message like this:

![Agent Out of Range](/static/courses/csintro/conditionals/act3-out-of-range.jpg)

Remember that sometimes restarting your code can be helpful if you find things are not working as they should.

1. Click the stop button in the lower-left corner of your code connection window.

![Stop Code](/static/courses/csintro/conditionals/stop-code.png)

1. You need to restart the coding environment. Click the play button. If the play button is not on, your code will not run in Minecraft.

![Play](/static/courses/csintro/conditionals/playbutton.png)

1. Saving your code again can restart your code as well, so let's do that for good measure. Save one more time and say **yes** to the warning message. 

![파일 저장](/static/courses/csintro/conditionals/save.png)

![Save Confirm](/static/courses/csintro/conditionals/save-override.png)

### ~

## Challenges

Let's change some things to make our own different and unique situations! Let's set up a `||player:on chat command||` that will check for two conditions. If the user enters **1**, the character will be teleported down to level 12 automatically. If the user enters **2**, the user will be teleported out of the ground.

### Challenge 1 - Set Up Conditions

Set up an `||player:on chat command "go"||`. Make this so `||player:on chat command "go"||` accepts a variable called **WhereTo**. Put an `||logic:if then else||` inside of go.

Test for these conditions:

1. User enters "1" (down)
2. User enters "2" (up)
3. User enters nothing

You will need to compare what the user enters and then add the following to the `||logic:if then else||`.

Put the following inside the up branch or 1:

```blocks
gameplay.setGameMode(
    GameMode.Creative,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    player.teleport(positions.createWorld(player.position().getValue(Axis.X), 100, player.position().getValue(Axis.Z)))
```

Put the following inside the down branch or 2:

```blocks
gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    player.teleport(positions.createWorld(player.position().getValue(Axis.X), 12, player.position().getValue(Axis.Z)))
```

Give the user a message if they enter nothing.

### Challenge 2 - Add More Conditions

What else could you do to make `||player:on chat command "go"||` from Challenge 1 better?

Options:

* What about equipping your character with torches automatically before going down? 
* You might clear out a small room so that after the character teleports they have some space.
* You could automatically teleport the agent to your character after you go down to level 12.

Choose at least one of the options above or your own modification and implement your option(s) for this challenge.

**Note**: The solution has all three preceding options included in it for demonstration.

## Experiments

Here, there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

## Experiment 1 - Standard Checkerboard

Have your agent build a checkerboard. Make sure slot 1 and 2 have blocks in the agent's inventory!

![Agent - Checkerboard 2](/static/courses/csintro/conditionals/checkerboard1.jpg)

![Agent - Checkerboard 1](/static/courses/csintro/conditionals/checkerboard2.jpg)

This uses a bit of math and a `||logic:if then else||` to alternate blocks and give that checkerboard look.

How could you change this? Could you make other patterns by playing with the `||logic:if then else||`?

![Agent - Checkerboard 2](/static/courses/csintro/conditionals/act3-checkerboard-experiment1.jpg)

Could you add ideas from other code you have seen to make this different and more interesting? What about one block up and the next down?

## Experiment 2 - Maze Digger

This is similar to an earlier activity. Here the agent will dig for you BUT it will generate a random maze. There are several concepts we have discussed as well as a new one, functions. Functions will be covered in the next lesson, so you should take a look at them.

The agent turns randomly with the help of a `||logic:if then else||` that checks what random number is generated.

How could you make this even more random? A cool maze definitely needs to be random! The natural features of the world will help, but what else could make this maze super fun? Maybe you could add animals or monsters as well!

![Random Maze 1](/static/courses/csintro/conditionals/act3-exper2-random-maze1.jpg)

![Random Maze 2](/static/courses/csintro/conditionals/act3-exper2-random-maze2.jpg)