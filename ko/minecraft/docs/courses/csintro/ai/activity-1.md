# Activity: Maze Generation

Learning how to read and write go hand in hand. To become better at writing code yourself, it is good practice to read other people's programs. Try to read and understand how they work. For this activity, instead of writing code, you will explore an existing program for creating a maze. You will try to answer the following questions:

### Questions

1. Describe what the `||blocks:fill||` block does.

2. Why do we Place a block of Air at `~0 ~0 ~0`?

3. Why do you think we set agent destroy obstacles to false?

4. What is the difference between the two Teleport commands?

## Do the activity

1. Launch Minecraft and create a new Flat world in creative mode

![Grass world template](/static/courses/csintro/ai/grass-template.jpg) You can use the Blocks of Grass template in Minecraft: Education Edition

![Minecraft flat world setting](/static/courses/csintro/ai/create-from-template.jpg)

2. Set the game mode to `Creative`, and World Type to `Flat`.

3. Open MakeCode in the Code Connection app

4. Select the **Import** button in MakeCode

![Code Connection homepage](/static/courses/csintro/ai/import-code.jpg)

5. Select the **Import URL** card

![Import URL button](/static/courses/csintro/ai/import-url.jpg)

6. Paste this URL in the text box and import the code: https://makecode.com/_9EP0Vt048K0U 

### ~

The code for this Maze Generation program is a bit more complex and developed in JavaScript. Basically, the Maze on chat command creates a 10 x 10 block of stone around the Player's location. The Dig function will instruct the agent to dig out the maze from this block of stone. If the agent breaks through a wall in the maze, it will patch it up using the blocks in the agent's inventory. The Shuffle function will 'shuffle' the directions that the agent will try digging in, to create a random maze pattern. You can preview the chat command "maze" in the blocks below:

```blocks
player.onChat("maze", function () {
    blocks.fill(
    blocks.block(Block.Stone),
    positions.create(-5, 0, -5),
    positions.create(5, 0, 5),
    FillOperation.Replace
    )
    agent.teleportToPlayer()
    blocks.place(blocks.block(Block.Air), positions.create(0, 0, 0))
    agent.setAssist(AgentAssist.DetroyObstacles, false)
    player.teleport(positions.create(0, 5, 0))
    player.say("let's dig that maze!")
    dig()
})
function dig() {

}
```

The agent will need materials to patch holes it makes in the maze. Because the agent is "learning" as it goes, it may accidently break a block of the maze wall only to later realize we need that block. Thus, the agent then patches the hole it made by mistake. you can give the agent some wood to patch the holes.

7. Give the agent some oak wood planks in its inventory, in the upper left inventory slot.

### ~ hint

To give your agent something to place, go over to your agent and right-click on it. Move some blocks from your player's inventory to your agent's inventory like shown in the picture below. The blocks must be put in that upper left-hand box or the agent will place nothing.

![Agent's inventory](/static/courses/csintro/ai/agent-add-oak-wood-plank-inventory.jpg)

### ~

Let's try out the program!

8. Type the command "maze" in the chat window to see the program run. Double tap the space bar and fly up to get a bird's-eye view of the agent while it works. It is important to stay clear while it builds the maze.

### Build the starting and ending locations

For the next activity, the agent will need to know when it has successfully completed the maze. In activity 2, you will be creating some code to get the agent to navigate the maze successfully. To get set up for the next activity, you will need to prepare the starting and ending areas of the maze.

### ~ hint

You will need to equip the player with a diamond pickaxe and redstone block. The pickaxe is to destroy the stone for the starting point and ending point. The redstone will mark the ending point. Open Terminal using '/', then type the give command to equip the player with a diamond pickaxe and a block of redstone.

    /give @s diamond_pickaxe 
    

    /give @s redstone_block 
    

### ~

Now all you need to do is build a starting and ending point.

9. Decide a starting point and an ending point. Most likely these will be on opposite ends of the maze.

10. Destroy a block at the starting point.

11. Destroy a block at the ending point. Place a redstone block underneath the ending point.

![Destroy area for ending location](/static/courses/csintro/ai/remove-grass-block.jpg)

After destroying the grass block that marks the ending location, place a redstone block in the dirt.

![Place redstone block at ending location](/static/courses/csintro/ai/place-redstone-blocks.jpg)

In the next activity, [Maze Pathfinding](/courses/csintro/ai/activity-2), you’ll have the agent stop when it detects redstone under its feet. This is how you will know it has completed the maze!

![Complete Maze Setup](/static/courses/csintro/ai/complete-maze.jpg)

## Activity reflection

### Questions

1. Describe what the `||blocks:fill||` block does.

2. Why do we Place a block of Air at `~0 ~0 ~0`?

3. Why do you think we set agent destroy obstacles to false?

4. What is the difference between the two Teleport commands?

### Answers

1. The `||blocks:fill With stone||` block creates a 10 x 10 block of stone around the Player's location. The agent will carve the maze out of this stone.

2. The agent starts at the center of the 10 x 10 block of stone and carves out a maze, so first we teleport the agent to the Player's coordinates, then place a block of air at that spot to free the agent up.

3. We set Destroy obstacles to false because we don't want the agent to destroy the blocks in front of it until we have a chance to inspect them. This helps us determine whether we are in an existing maze pathway or not.

4. The first `||player:teleport to||` block teleports the agent to the Player's location, which is at the center of the maze. The second teleport block teleports the Player to a spot five blocks above the maze, for a bird's-eye view.

Maze generation algorithms are a popular programming exercise because there are as many different approaches as there are types of mazes! It's also fun to see the maze as it's being created. The maze generation routine we are using here is adapted from an algorithm called "recursive backtracking".

### Maze pseudocode

Here is the maze solution in pseudocode:

    Shuffle the array:
        Create an array of three directions
        Randomize their order
    
    For each value in the array:
        If it's left,
            turn left
        If it's right,
            turn right
        If there's a wall in front of us (empty on the other side),
            preserve the wall
        If there's no wall in front of us,
            dig a path forward (recursively by calling the same function "dig" again)
        Back up 2 spaces
        Turn back to original direction 
    

The main idea is that the agent will continue to carve an erratic path through the solid block until it reaches a blank space, trying not to destroy walls between passages. Notice that at the very end it calls the same function again in order to restart the maze carving. This is a special form of iteration known as *recursion*.

## 챌린지

Let's change some things to make our own different and unique situations!

### Challenge 1 - Give the Player a Perch for the Bird's-Eye View

A minor issue is that we don't have anything to stand on and watch the agent build if we choose to. It would be nice to be teleported up to a block when the maze starts. We can then watch comfortably.

**Tasks**

1. Add a block for the player to stand on
2. Teleport the player up to that block.

![Perch for Better View 1](/static/courses/csintro/ai/act1-challenge1-bird-perch1.jpg)

![Perch for Better View 2](/static/courses/csintro/ai/act1-challenge1-bird-perch2.jpg)

The solution has a bookshelf block as the perch but you could use any block you want.

![Perch for Better View 3](/static/courses/csintro/ai/act1-challenge1-bird-perch3.jpg)

### Challenge 2 - Redecorate the Maze

Change what the maze walls are made of, the patches, and add a floor of a different block type. In total you would need to select 3 new block types to completely redecorate.

**Block Types to Change:**

1. Initial Maze or Block
2. Wall Patch (equip the agent with a different block for patching the holes it makes by accident)
3. New Floor

Answers will vary...

![Redecorated Maze](/static/courses/csintro/ai/act1-challenge2-redecorated-maze.jpg)