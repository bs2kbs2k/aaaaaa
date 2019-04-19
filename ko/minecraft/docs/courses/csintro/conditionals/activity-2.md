# Activity: Agent Tree Chopper

Chopping trees for wood is hard work but necessary in Minecraft if you want to craft objects and tools in Survival mode. But you can automate this chore through code with the help of our agent! Let’s teach the agent how to chop down a tree of any height and return back down to the ground.

When you start a new MakeCode project, it’s often a good idea to plan out what steps you want to take before you start coding.

Here’s what you’ll want to do:

1. Figure out how tall the tree is: >* As long as there’s a block in front of the agent, keep moving up. >* Keep track of how tall the tree is.
2. Repeat the following the same number of times as the tree is tall: >* Destroy the block in front of you. >* Move down.
3. Collect everything.

# A Different Conditional

The last activity used `||logic:if then else||` statements to check conditions and perform actions the way you wanted them done. In this activity, you will use conditionals in a `||loops:while||` loop. The agent will continue moving up as long as there is a block of tree to climb.

## Do the activity

### Make a project

1. Create a new MakeCode project called **Chopper**.

2. Rename the existing `||player:on chat command||` to `"tp"`.

3. From `||agent:AGENT||`, drag an `||agent:agent teleport to player||` block inside `||player:on chat command "tp"||`.

4. Now, let’s also create a directional command so we can turn our Agent around. You can right-click on `||player:on chat command "tp"||` and select **Duplicate** to make a copy.

5. Rename the duplicate `"lt"`.

6. Delete the inside block for this new duplicate and replace `||agent:agent teleport to player||` with `||agent:agent turn 'left'||`.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
```

### Create the `height` variable

7. From `||player:PLAYER||`, drag a `||player:on chat command||` block into the coding Workspace and rename it `"chop"`.

8. You’ll use a variable to keep track of the height of the tree. In the `||variables:VARIABLES||` Toolbox drawer, click the **Make a Variable** button.

9. Name the new variable `height`.

![Make a new variable named 'height'](/static/courses/csintro/conditionals/height-variable.jpg)

### Initialize `height` to zero

10. From `||variables:VARIABLES||`, drag out `||variables:set||` and snap it inside `||player:on chat command "chop"||`.

11. In the `||variables:set||` block, use the drop-down menu to select `height` as the variable and set `height` to `0`.

```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
})

```

### Start at the base of a tree

Let's assume the agent is placed facing the base of the tree when the chop command is given. You use the `"tp"` and `"lt"` commands to get your agent in place and then finally `"chop"`.

Use a `||loops:while||` loop, which is like a `||loops:repeat||` loop combined with a conditional statement. Here the code will continue as long as there is a block in front of the agent. If there is a block in front of the agent, then it will keep moving up the tree.

12. From `||loops:LOOPS||`, drag out a `||loops:while||` loop and drop it under `||variables:set 'height'||`. This would be inside `||player:on chat command "chop"||`.

13. From `||agent:AGENT||`, drag out `||agent:agent detect 'block' 'forward'||` and drop it into the `||loops:while||` loop replacing `||logic:true||`.

```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {

    }
})
```

### Move up the tree and chop

Finally, you get to do some chopping--or at least the agent does!

14. From `||variables:VARIABLES||`, place a `||variables:change||` block inside the `||loops:while||` loop.

15. The new block should read `||variables:change 'height' by 1||`. This will increase the height variable by 1 each time the agent moves up. This is how we can keep track of the height of the tree.

16. If leaves or branches are above the agent’s head, you need to destroy them in order to move the agent up. From `||agent:AGENT||`, place `||agent:agent destroy||` below `||variables:change 'height' by 1||`. You will need to adjust this block by selecting `up` as the direction from the drop-down menu.

17. Finally, get your agent to move up. Grab a `||agent:agent move||` block, and then use the drop-down menu to select `up` as the direction like you did in the previous step.

```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
        height += 1
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    }
})
```

### Come back down

After the agent reaches the top of the tree (there is no longer a block in front of it) the height of the tree will be stored in the variable height. Then you’ll want another loop that will destroy the block in front of the agent (the tree trunk) as the agent moves down. This loop should run as many times as the height of the tree.

18. From `||loops:LOOPS||`, drag out a `||loops:repeat||` loop, and drop it after the `||loops:while||` loop in your `||player:on chat command "chop"||`.

19. From `||variables:VARIABLES||`, drag out `height` and replace the `4` in the `||loops:repeat||` loop.

```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
        height += 1
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    }
    for (let i = 0; i < height; i++) {

    }
})
```

### Chop while you drop

At this point the agent should be standing at the top of a tree. You need to get it to climb back down, chop the tree, and collect the wood.

20. From `||agent:AGENT||`, place a `||agent:move||` and `||agent:destroy||` inside the `||loops:repeat||` loop.

Now you need to adjust these blocks for the situation. The agent needs to **move down** and will be chopping each piece of the tree that is **in front** of it.

21. In the `||agent:move||` block, select `down` as the direction. The agent will move down. Then, the agent should destroy the tree block in front of it. The default settings are ok for `||agent:destroy||`.

Finally, you want your agent to collect all the wood it chopped.

22. From `||agent:AGENT||`, place `||agent:agent collect all||` after the `||loops:repeat||` loop. This is now the last block in our `||player:on chat command||` for `"chop"`.

### Complete program

```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
        height += 1
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    }
    for (let i = 0; i < height; i++) {
        agent.move(SixDirection.Down, 1)
        agent.destroy(SixDirection.Forward)
    }
    agent.collectAll()
})

```

**Shared Program:** https://makecode.com/_1hFLi6X1qPcJ

![Agent - Tree Chop Start Prep](/static/courses/csintro/conditionals/treechopstart1.jpg)

![Agent - Tree Chop Start Correct Facing](/static/courses/csintro/conditionals/treechopstart2.jpg)

![Agent - Tree Chop Finish](/static/courses/csintro/conditionals/treechopend.jpg)

## Challenges

It would be nice to have the agent teleport as part of `||player:on chat command "chop"||`. It is hard to predict which direction the agent will be facing after you teleport it. The directional commands ("tp" and "lt") work, but one command would be more efficient.

Can we automate this? After completing these two challenges, you should be able to accomplish this. First, think about the problem.

You want to:

1. Teleport the agent.
2. Turn the agent until it finds the base of the tree.
3. Begin climbing and run the code we already made.

The only potential drawback to this plan is that you would still need to stand directly at the base of the tree in order for the agent to start in the right place. Low branches might need to be cleared. Perhaps as a bonus you might figure out how to fix this issue as well, but first complete Challenges 1 and 2.

### Challenge 1 - Teleport Agent and Get Some Things Set Up for Challenge 2

1. Can you have the agent teleport as part of `||player:on chat command "chop"||`?

After that you will need some things to accomplish Challenge 2. Please create the following:

2. Create a variable called `TurnToTree` and set this to `true`.

3. Create a while loop that makes the agent turn left or right.

Test your code!

What happened? Oh no, you are stuck in another infinite loop. `TurnToTree` is `true`, so your new while loop just keeps going and going. Therefore, your agent just keeps spinning and spinning.

![Stop Code](/static/courses/csintro/conditionals/agent-keeps-spinning.jpg)

Read below how to stop this...

### ~ hint

If you are caught in an infinite loop, you will need to stop your code from the code connection window.

1. Click the stop button in the lower-left corner of your code connection window.

![Stop Code](/static/courses/csintro/conditionals/stop-code.png)

2. Restart the coding environment. Click the play button. If the play button is not on, then your code will not run in Minecraft.

![Play](/static/courses/csintro/conditionals/playbutton.png)

3. Saving your code again can restart your code as well, so do that for good measure. Save one more time and say **yes** to the warning message. 

![파일 저장](/static/courses/csintro/conditionals/save.png)

![Save Confirm](/static/courses/csintro/conditionals/save-override.png)

### ~

This is ok because now you are prepared for Challenge 2, but you need to figure out a way to stop the agent when he sees the tree.

### Challenge 2 - Have the Agent Face the Tree Automatically

You are now ready to solve the second task.

2. Turn the agent **until it finds the base of the tree**.

To do this, you will need to set `TurnToTree` to `false` inside the while loop, but you need a condition for this. You want the agent to stop when it finds the tree.

### ~ hint

There is no find block for the agent, but there is a detect block. Maybe this could be useful?

![Save Confirm](/static/courses/csintro/conditionals/act2-challenge2-detect.png)

This block returns `true` or `false` if the agent detects or finds a block in the direction you tell it.

### ~

How could you test this condition and then stop the agent from turning? You need to set `TurnToTree` to `false`, but where and how?

## Experiments

Here, there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Increase the Size of the Hole

The agent works hard for you! You can get it to dig for you too. Enter the on chat command **dig 4** to try out this code.

Can you get the agent to dig and place something at the same time? Can you increase the size of the hole? Right now, it is 2 x 2. You might get the agent to dig a 4 x 4 hole and line it with gold as it goes down.

![Agent - Dig 4](/static/courses/csintro/conditionals/dig1.jpg)

### Experiment 2 - Create a Maze

This experiment code is aimed at getting you to think about how you might build some code to create a tunneling robot. The agent will accept two numbers this time. First, it digs down and then will dig horizontally.

Enter the on chat command **dig 5 4** to try out this code.

How could you get your agent to build an underground maze? What else might you do with this underground hole it is digging? You could fill it with lava or put some mobs down there or even build an underground home. What other pieces of code might help you do this?

![Agent Digs Down and Horizontally](/static/courses/csintro/conditionals/act2-exp2.jpg)