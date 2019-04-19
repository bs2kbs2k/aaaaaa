# Activity: Tree Hunter

You might recall that an activity in the [Conditionals Lesson](/static/courses/csintro/conditionals), [Agent Tree Chopper](/static/courses/csintro/conditionals/activity-2) chops down individual trees. However, it requires an intelligent player to stand at the base of a tree and teleport the agent to the tree each time. Imagine if you could turn a more intelligent agent loose in a grove of trees! Your mini tree chopping AI could find the trees and chop them down automatically while you have a glass of lemonade.

### ~ hint

The way this code is set up it will work with trees that have trunks that are one block. Trees with bigger trunks like the tree in the picture below might not be chopped completely.

![Trees with Thick Trunks Not Chopped Completely](/static/courses/csintro/ai/act3-thick-trees.jpg)

### ~

When you see a grove of trees, it's always easy to see the next tree to chop down. However, the agent can only inspect blocks that are immediately forward, to the left, or to the right of its current position. To imagine how to code an intelligent agent, picture yourself working your way through a grove of trees, blindfolded. How might you proceed?

There are a few things to consider:

1. How will the agent approach the task?
2. What about changing elevation and terrain?
3. The agent actual needs to chop down a tree. (No problem! [Conditionals Lesson](/static/courses/csintro/conditionals), [Agent Tree Chopper](/static/courses/csintro/conditionals/activity-2))

4. One way to solve this problem is to divide the grove into a grid and proceed through the grid row by row. It's slow, but you will eventually inspect every square on the grid. To make this a little bit more efficient you'll test forward, left, and right at every step. This will reduce the number of passes your agent will need to make.

![Grove grid](/static/courses/csintro/functions/grove-grid.jpg)

2. You also need to plan for the changing terrain. Trees rarely grow on a flat plain in Minecraft. There are usually some changes in elevation and you will want to make sure the agent follows the natural ground terrain so that it always starts at the base of each tree. 

In this activity, the agent will be able to handle one block of elevation change at a time while searching the grid so choosing a grid that is fairly flat is ideal for optimal success. However, we are studying AI and that is also about testing and experimenting. Try using a smaller grid size at first and don't get too bothered if the agent gets off track a little. Try to examine what it is doing if things go wrong and figure out why its behavior is not what should be expected! Perhaps you can learn from its mistakes or even improve the current code with modifications!

![Terrain - One block of elevation](/static/courses/csintro/ai/terrainOneBlockTall.png)

3. Finally, your agent has to actually chop down the tree. Fortunately, as was mentioned, you have already coded this part so you can go back to the [Conditionals Lesson](/static/courses/csintro/conditionals), [Agent Tree Chopper](/static/courses/csintro/conditionals/activity-2) and reuse that code. 

![Agent - Tree Chop Start Prep](/static/courses/csintro/conditionals/treechopstart1.jpg)

![Agent - Tree Chop Start Correct Facing](/static/courses/csintro/conditionals/treechopstart2.jpg)

![Agent - Tree Chop Finish](/static/courses/csintro/conditionals/treechopend.jpg)

This Tree Hunter program is fairly complex but we can leverage the organizational benefits of functions to divide our problem into clear individual tasks:

## Main Program, *"runchopper"*, that runs all our functions below in the right order

* Searching for Trees (search function)
* Following the Terrain (follow function)
* Turning around at the end of a row (turn function)
* Chopping Trees (chop function)

## Do the activity

In order to make this activity more managable, starter code has been provided. We can get the starter code by importing the beginning of the project into the MakeCode editor:

* Open MakeCode in the Code Connection app
* Select the Import button in MakeCode
* Select the Import URL card
* Paste this URL in the text box: https://makecode.com/_3kvApt5MgbpL

The starter code is also available below:

```typescript
let flipturn = false
let height = 0
function chop() {
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
}
function follow() {
    agent.move(SixDirection.Forward, 1)
    if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.Grass)) {
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    } else if (!(agent.detect(AgentDetection.Block, SixDirection.Down))) {
        agent.move(SixDirection.Down, 1)
    } else {

    }
}
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
function turn() {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    if (flipturn) {
        agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Right)
    } else {
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
    }
    flipturn = !(flipturn)
}
```

This starter code gets us some of the way to the goal. We now have only the bolded items below left to complete.

1. **Main Program that runs all our functions below in the right order >> *"runchopper"***
2. **Searching for Trees (search function)**
3. Following the Terrain (follow function)
4. Turning around at the end of a row (turn function)
5. Chopping Trees (chop function)

### Make the *"runchopper"* command

1. Create a `||player:on chat command||` block and rename it `"runchopper"`.

To determine the size of the area to search, let's attach a number as a parameter to our `"runchopper"` command block that will represent the length of one side of the square search area. For example, if we call `"runchopper 8"` we want our agent to search within a 8 x 8 block square area, which should encompass at least a few trees.

![Identify search area](/static/courses/csintro/ai/identify-search-area.jpg)

2. Click the plus sign **(+)** in `||player:on chat command "runchopper"||` to add the `num1` parameter to our block. Use the dropdown to rename `num1` to `area`.

```blocks
player.onChat("runchopper", function(area) {

})
```

### Create the *"search()"* function

Let's create the remaining function that will make up our program. Then at the end we will call all of our functions from `||player:on chat command "runchopper"||`. This search function will have a lot of code that is the AI. It will allow the agent to intelligently decide if it has found a tree or not.

3. Click the **ADVANCED** tab on the Toolbox to display the additional Toolbox categories.

4. From `||functions:FUNCTIONS||`, click the **Make a Function** button.

5. Name the function: `search`.

### Add logic to the *search()* function

The *search()* function, which will have the agent check to see if there are any trees around it. The agent will check to the right, the left, and in front for wood blocks indicating a tree. If it finds a wood block, it will call the *chop()* function to chop the tree down.

6. From `||logic:LOGIC||`, drag an `||logic:if then else||` into `||functions:function search||`.

7. In the `||logic:if then else||`, click the plus sign **(+)** two times to create two additional `||logic:else if||` clauses.

```block
function search() {
    if (true) {

    } else if (false) {

    } else if (false) {

    } else {

    }
}
```

#### Look for some wood on the left

Let's first see if there is a block of wood to the left of the agent.

8. From `||logic:LOGIC||`, drag out a `||logic:0 = 0||`, comparison block. Put this comparison into the first conditional slot for the `||logic:if||` statement.

9. From `||agent:AGENT||`, drag an `||agent:agent inspect||` block into the first slot of the `||logic:0 = 0||`.

10. In `||agent:agent inspect||`, use the drop-down menu to select `left` as the direction to inspect.

11. From `||blocks:BLOCKS||`, drag out a `||blocks:block||` and drop this in the second slot of the `||logic:0 = 0||`.

12. In `||blocks:block||`, use the drop-down menu to select an `Oak Wood` block or a type of tree in the area you want to search.

This tests to see if there is Oak Wood and if there is the agent will need to chop it!

```blocks
function search() {
    if (agent.inspect(AgentInspection.Block, SixDirection.Left) == blocks.block(Block.LogOak)) {

    } else if (0 == 0) {

    } else if (0 == 0) {

    } else {

    }
}
```

### Chop to the left

If you do find some wood to the left of the agent, then you will want to turn the agent left and call the *chop()* function to chop down the tree. Finally, you will want the agent to turn back around and face forward again.

13. From `||agent:AGENT||`, put an `||agent:agent turn||` into the first branch of the `||logic:if then||`.

14. From `||functions:FUNCTIONS||`, place a `||functions:call function chop||` under the `||agent:agent turn||`.

15. Duplicate the `||agent:agent turn||` and place the copy below `||functions:call function chop||`.

16. In this new `||agent:agent turn||`, use the drop-down menu to select `right`. This will turn the agent back after the tree gets chopped down.

```blocks
function search() {
    if (agent.inspect(AgentInspection.Block, SixDirection.Left) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (false) {

    } else if (false) {

    } else {

    }
}
function chop()  {

}
```

### Look for wood to chop straight ahead

Now, you want check for wood in front of your agent. In this case, you don't need to turn the agent.

17. Click on the first condition we made and duplicate it.

![Duplicate Search Condition 1](/static/courses/csintro/ai/act3-duplicate-search-first-cond.png)

18. Snap the duplicate into the condition slot of the second branch of your `||logic:if||`.

Now just make a few adjustments.

19. In `||agent:agent inspect||` change the direction to `forward`.

20. Duplicate `||functions:call function chop||` and place it inside this branch(2nd branch) of the `||logic:if||`.

```blocks
function search() {
    if (agent.inspect(AgentInspection.Block, SixDirection.Left) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.LogOak)) {
        chop()
    } else if (false) {

    } else {

    }
}
function chop() {

}
```

### Look for wood to chop on the right

Finally, you should see if there is a block of wood to the right of the agent. This is essentially the same as looking to the left but several things will be opposite.

21. Click on the first condition we made and duplicate it again. Place this in the third branch of the `||logic:else if||`.

22. Adjust the direction to `right`.

23. You will need two `||agent:agent turn||` blocks. Duplicate two and put them inside the third branch.

24. Duplicate `||functions:call function chop||` and place it between the two `||agent:agent turn||` blocks.

25. Now, just adjust the turns. This time the agent turns right first, chops, and then turns back to the left.

The final else branch of your `||logic: if||` will be left blank.

```blocks
function search() {
    if (agent.inspect(AgentInspection.Block, SixDirection.Left) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.LogOak)) {
        chop()
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Right) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Right)
        chop()
        agent.turn(TurnDirection.Left)
    } else {

    }
}
function chop() {

}
```

### Allow the agent to destroy obstacles in its path

What is the best way to ensure the agent moves over terrain?

Let's create a block to allow the agent to deal with obstacles above it. If the agent can’t move because of an obstacle above it, then this block will destroy the obstacle, before the agent moves.

The agent has a block that will give it some extra powers that are useful in this case. The block is called set Assist and it is located in the `||agent:AGENT||` Toolbox drawer BUT it does not say set Assist on it. The block looks like this:

```block
agent.setAssist(AgentAssist.PlaceOnMove, false)
```

### ~ hint

Check out other cool things this block can do by searching for it in the help! It can allow your agent to place blocks automatically when it moves and also place blocks from any slot in its inventory instead of just using the upper left hand inventory slot.

### ~

26. From the `||agent:AGENT||` Toolbox drawer, drag a `||agent:set assist||` block into `||player:on chat command "runchopper"||`.

27. In the `||agent:agent assist||`, use the drop-down menu to select `destroy obstacles`.

28. Finally, select `||logic:true||`.

```block
agent.setAssist(AgentAssist.DetroyObstacles, true)
```

### Control the agent's turn direction

You need the agent to turn around at the end of each row. What this means is the agent needs to turn alternately left and then right at the end of each row.

![Agent turn path](/static/courses/csintro/functions/agent-turn-pattern.jpg)

What is the best way to ensure the agent alternates its turns?

Let's create a Boolean variable to keep track of which direction to turn. Recall from the [Variables Lesson](/static/courses/csintro/variables) that a Boolean variable has only two possible values: True or False. We'll use `||logic:true||` to denote a Right turn and `||logic:false||` to represent a Left turn. After we make our turn, we'll switch the boolean variable.

The variable **flipturn** was created as part of the starter code at the beginning of this activity. This is meant to be your Boolean variable.

29. From `||variables:VARIABLES||`, drag a `||variables:set||` block into `||player:on chat command "runchopper"||`.

30. In the `||variables:set||` block, use the drop-down menu to select `flipturn`.

31. From `||logic:LOGIC||`, drag a `||logic:false||` block into the `||variables:set||` and replace the `0`.

```blocks
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    flipturn = false;
})
```

We have everything in place. Now we just need to build it out. To move the agent through its search you will:

1. Get the agent to move down one row of the grid
2. Turn at the end
3. Continue going down rows until the square area is complete

### Put *search()* and *follow()* into the chat command

Now that we have all our functions built, let's bring it all together. For each step, we want our agent to Search for trees, and follow the ground terrain. By searching the agent will be actually searching three rows at a time because it searches left, right, and forward with each step.

![Agent Searches Three Blocks Above](/static/courses/csintro/ai/agent-searches-one-row.png)

32. From `||loops:LOOPS||`, drag a `||loops:repeat||` block into `||player:on chat command "runchopper"||`. Place this below the `||variables:set flipturn||` block.

Remember, that the `area` argument is the number of blocks in each row.

33. From `||variables:VARIABLES||`, drag `area` into the `||loops:repeat||` block replacing the default `4`.

Now the agent will search for all the blocks in one row, how ever many the user specifies.

34. From `||functions:FUNCTIONS||`, drag the `||functions:call function search||`, and the `||functions:call function follow||` blocks into the `||loops:repeat||` loop.

```blocks
let area = 0
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    flipturn = false
    for (let i = 0; i < area; i++) {
        search()
        follow()
    }
})
function search() {

}
function follow() {

}
```

### Add the *turn()* function to turn at the end of a row

Now, at the end of each row, we want to turn our agent around.

35. From `||functions:FUNCTIONS||`, drag the `||functions:call function turn||` and place this underneath the `||loops:repeat||` loop.

```blocks
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    flipturn = false
    for (let i = 0; i < area; i++) {
        search()
        follow()
    }
    turn()
})
function search() {

}
function follow() {

}
function turn() {

}
```

### Complete a Square Search Grid

You will need to add one more `||loops:LOOP||` so the agent searches the complete grid and completes the square instead of just searching three rows.

Because the agent is searching three blocks every step, it will not need to loop for the full area given. We would divide the area given by 3. In the example below, the agent is searching a 9x9 grid but as you can see it only needs to walk down the rows 3 times to do so.

![Grove grid](/static/courses/csintro/functions/grove-grid.jpg)

It only needs to search 3 times because it searches forward, left, and right every step. Another visual is given below. The blocks that are gray would be searched.

![Agent Searches Three Blocks Above](/static/courses/csintro/ai/act3-agent-searches-3-blocks1.jpg)

![Agent Searches Three Blocks](/static/courses/csintro/ai/act3-agent-searches-3-blocks2.jpg)

With that said, you need a `||loops:LOOP||` to handle this.

35. From `||loops:LOOPS||`, drag another `||loops:repeat||` loop out on the workspace. This new `||loops:repeat||` loop should enclose everything below `||variables:set flipturn||`.

36. From `||math:MATH||`, drag a `||math:0 ÷ 0||` block into the `||loops:repeat||` loop replacing the default `4`.

37. From `||variables:VARIABLES||`, drag `||variables:area||` into the first slot of the `||math:0 ÷ 0||`.

38. In the `||math:area ÷ 0||` block, type `3` in the second slot.

```blocks
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    flipturn = false
    for (let i = 0; i < area / 3; i++) {
        for (let i = 0; i < area; i++) {
            search()
            follow()
        }
        turn()
    }
})
function search() {

}
function follow() {

}
function turn() {

}
```

Here is the final code:

```blocks
let flipturn = false
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("runchopper", function (area) {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    flipturn = false
    for (let i = 0; i < area / 3; i++) {
        for (let i = 0; i < area; i++) {
            search()
            follow()
        }
        turn()
    }
})
function search() {
    if (agent.inspect(AgentInspection.Block, SixDirection.Left) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.LogOak)) {
        chop()
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Right) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Right)
        chop()
        agent.turn(TurnDirection.Left)
    } else {

    }
}
function follow() {
    agent.move(SixDirection.Forward, 1)
    if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.Grass)) {
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    } else if (!(agent.detect(AgentDetection.Block, SixDirection.Down))) {
        agent.move(SixDirection.Down, 1)
    } else {

    }
}
function turn() {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    if (flipturn) {
        agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Right)
    } else {
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
    }
    flipturn = !(flipturn)
}
function chop() {
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
}
```

To test this out be sure you first teleport your agent to your location using the provided `||player:on chat command "tp"||`

**Shared Project**: https://minecraft.makecode.com/40339-75969-92793-36604

## Challenges

Let's examine this code and given comments and feedback to tell what is going on.

### Challenge 1 - Create Comments to Show You Understand What Each Part of the Code Does

Create comments for the following blocks that have question marks.

![Make Comments for these Blocks](/static/courses/csintro/ai/act3-challenge1-comment-blocks.png)

You create comments by right-clicking on a block and selecting comment.

Your job is to determine what comment you should write. The comment should describe what task all the blocks inside these containers do.

Answers may vary but they should be something like the solutions given.

### Challenge 2 - Agent Gives Feedback

Have the agent give feedback using the blocks below. These `||player:say||` blocks will be in several different places throughout the code when you finish but are put together in one set of blocks here to start. Can you place these blocks in the appropriate places in the code?

```block
player.say("Need to Move Up")
player.say("Tree found in front of me")
player.say("Finished a row and turning left!")
player.say("Moving Down to the Ground")
player.say("Tree found on the left")
player.say("Chopping Tree...")
player.say("Tree found to my right")
player.say("Finished a row and turning right!")
```

This will further show that you understand what each piece of the code is doing.