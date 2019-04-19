# Activity: Maze Pathfinding

Now let's teach the agent how to navigate a maze on its own. Rather than giving the agent a set series of directional commands to solve one particular maze, you are going to need to use conditional statements to teach the agent how to find its way through any maze, intelligently.

You first need a maze to start out with. In case you missed this, the code from the previous activity, [Maze Generation](/static/courses/csintro/ai/activity-1), builds a maze for you. The activity asks you to place a redstone at the end of the maze. This is how your code will know when the agent has finished the maze. The agent will detect this redstone under its feet to signal the end of the code.

![Stone maze with redstone at the end](/static/courses/csintro/ai/agent-starting-location.jpg)

## The Algorithm

In any maze or labyrinth, you can always find your way out by following one wall consistently. You may not find the most direct way out, but you will always come out on the other side. In a Minecraft maze, this basically means always turn left whenever you can, and when you reach a dead end, turn around.

So, our simple maze-following algorithm looks like:

    As long as you aren't standing on redstone:
        If there is no block to the left of you,
            turn left and move forward.
        Otherwise, if there is no block in front of you,
            move forward.
        Otherwise, if there is no block to the right of you,
            turn right and move forward.
        Otherwise,
            turn around and move forward.
    

## Do the activity

### Try to code it yourself!

Try to code a way for the agent to get to the ending point on your own without following the activity steps. If the agent gets stuck, go ahead and use the steps to complete the program.

### Make a new project

1. Create a new MakeCode project called "Pathfinder".

2. Use this starter code from the [Introduction to the Agent](/courses/csintro/iteration/activity-1) activity. This code allows you to easily position the agent.

```typescript
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
```

You can copy the preceding code by highlighting the code, pressing Ctrl+C to copy, and then pasting (Ctrl+V) the code into the JavaScript side in your code connection.

![Switch code to JavaScript view](/static/courses/csintro/ai/act4-javascript.jpg)

Let's use the basic agent controls to move the agent to the starting point of the maze.

3. Move your player to the start of the maze. Type the command "tp" into the chat window. Your agent should teleport over there. Then you will need to turn the agent left("lt") or right("rt") to get it facing inwards.

![Agent Sitting Just Inside the Door](/static/courses/csintro/ai/act2-agent-at-start.jpg)

![Agent at Starting Location](/static/courses/csintro/ai/act2-agent-at-start2.jpg)

4. Create an `||player:on chat command||` block and rename it to `"mr"` which stands for maze runner.

You'll put the whole algorithm in a `||loops:while||` loop, which will tell your agent to continue searching for the end of the maze as long as it isn't standing on `redstone`.

5. From `||loops:LOOPS||`, drag a `||loops:while||` loop into `||player:on chat command "mr"||`.

6. From `||logic:LOGIC||`, put a `||logic:not||` block into the `||loops:while||` loop replacing the true.

7. From `||agent:AGENT||`, drag an `||agent:agent detect||` into the `||logic:not||`.

8. In the `||agent:agent detect||` block, use the drop-down menu to select `redstone` as the type of block to detect.

9. In the `||agent:agent detect||` block, use the drop-down menu to select `down` as the direction.

```blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
    }
})

```

This essentially means that while the agent doesn't detect redstone beneath it, your code will continue running.

### Check for a path to the left

Next, we'll check to see if there is a path open to the left and if so, turn left and move forward.

10. From `||logic:LOGIC||`, drag an `||logic:if then else||` block into the `||loops:while||` loop.

11. Again from `||logic:LOGIC||`, drag a `||logic:not||` block into the `||logic:if then||` conditional slot replacing the `true` block.

12. From `||agent:AGENT||`, drag an `||agent:agent detect||` into the `||logic:not||` block.

13. In the `||agent:agent detect||` block, use the drop-down menu to select `left` as the direction to look.

```blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {

        } else {

        }
    }
})

```

### Turn and move forward

If the Agent doesn't detect a block to its left, then we want the Agent to turn left and move forward.

14. From `||agent:AGENT||`, drag an `||agent:agent turn||`, and an `||agent:agent move||` block into the first branch of your `||logic:if then||`.

```block
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
        } else {
        }
    }
})
```

### Check for a path forward or to the right

Now we need to add 2 more conditions to check forward and to the right of the Agent.

15. Click the Plus **(+)** sign at the bottom of the If then else block twice, to add 2 more `||logic:Else if||` clauses.

```blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {

        } else if (false) {

        } else if (false) {

        } else {

        }
    }
})

```

### Duplicate Conditions for the Other Branches of Your If

16. Right-click on the `||logic:not||` block in the first If then conditional slot, and select Duplicate – do this twice to create two more `||logic:not||` `||agent:agent detect||` conditions.

17. Drop these duplicated conditions into the two additional `||logic:else if||` slots.

18. In the second branch of the `||logic:else if||`, use the drop-down menu to select `forward` as the direction to check. Thus, we are checking left and then forward.

19. In the third branch of the `||logic:else if||`, use the drop-down menu to select `right` as the direction to check. Thus, we are checking left, forward, and then right.

```blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Right))) {
        } else {
        }
    }
})
```

### Move ahead forward

If the agent doesn't detect a block in front of it, then it should simply move forward.

20. From `||agent:AGENT||`, drag an `||agent:agent move||` block into the second branch of the `||logic:else if||` clause.

### Move along to the right

If the agent doesn't detect a block to its right, then the agent should turn right and move forward.

21. From `||agent:AGENT||`, drag an `||agent:agent turn||`, and an `||agent:agent move||` block into the third branch of the `||logic:else if||` clause.

22. In the `||agent:agent turn||` block, use the drop-down menu to select `right` as the direction to turn.

**You may also want to just duplicate these blocks. That is perfectly fine as well!**

```blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Right))) {
            agent.turn(TurnDirection.Right)
            agent.move(SixDirection.Forward, 1)
        } else {
        }
    }
})
```

### Turn around and go backward

Finally, if the agent is at a dead-end (none of the three directions are open), you want the agent to turn around and head back in the opposite direction.

23. From `||agent:AGENT||`, drag the following 3 blocks into the last `||logic:else||` clause: 2 `||agent:agent turn||` blocks, and an `||agent:agent move||` block.

```blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Right))) {
            agent.turn(TurnDirection.Right)
            agent.move(SixDirection.Forward, 1)
        } else {
            agent.turn(TurnDirection.Left)
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
        }
    }
})

```

### Found the redstone!

24. If the agent detects Redstone, it will know it has reached the finish. You can have the agent do a happy dance at the end of the maze! Feel free to reuse the code from the [Dance Dance Agent](/courses/csintro/iteration/activity-2) activity in [Lesson 5: Iteration](/courses/csintro/iteration).

```typescript
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Left, 1)
    }
})
```

25. To run the code for `||player:on chat command "dance"||`, place a `||player:run chat command ""||` block from `||player:PLAYER||` underneath and outside the `||loops:while||` loop. It should read `||player:run chat command "dance"||` when you are finished.

### ~hint

Using `||player:run chat command "dance"||` is like making a function call. You could use a function here instead if you wanted to.

### ~

### Complete program

```blocks
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Right))) {
            agent.turn(TurnDirection.Right)
            agent.move(SixDirection.Forward, 1)
        } else {
            agent.turn(TurnDirection.Left)
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
        }
    }
    player.runChatCommand("dance")
})
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Left, 1)
    }
})

```

**Shared Program:** https://makecode.com/_M8HXrKRLfhzM

## Challenges

### Challenge 1 - Fool the AI

How can you break this code or activity? Find a way to break this and describe why it confuses the agent or why it is not working.

### Challenge 2 - Agent Feedback

Can you have the agent notify the player after the decisions it makes? The messages could say things like "Oh! Better turn left, I hit a wall!" There are several ways to do this.

![Agent Gives Feedback on Progress](/static/courses/csintro/ai/act2-challenge2-feedback.jpg)

### Challenges 3 - Leave Trail of Breadcrumbs

Can you find a way for the agent to mark the trail it takes. This might help others find there way through should they stumble upon the maze. The solution has the agent tilling dirt to show the way but perhaps you can think of other ways to mark the path.

![Breadcrumbs](/static/courses/csintro/ai/act2-challenge3.jpg)

![Breadcrumbs from Above](/static/courses/csintro/ai/act2-challenge3-above.jpg)