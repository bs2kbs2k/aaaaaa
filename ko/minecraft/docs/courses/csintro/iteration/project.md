# Independent Project

As you move through the lessons, it is important to try and challenge yourself. Look at code you don't understand and try to take ideas from it. Copy and paste, change it, and make it your own. Think of outside ideas that you might try that might not be mentioned in lessons. Be able to take an abstract goal of just a few words and make code to accomplish it.

This is why the project for [Lesson 5](/courses/csintro/iteration) is a bit different from previous projects. This independent project is an opportunity for you to show what you know. In this lesson, you learned about how `||loops:LOOPS||` can reduce the size of your code by repeating certain tasks for you. Now, your challenge is to come up with a MakeCode project that uses iteration in some way to create a stairway to diamonds.

One of the most valuable resources in Minecraft are diamonds. You can find diamonds deep underground in **Survival** mode. Getting from the surface down to where diamonds are found is challenging. Luckily, you can program your agent to do this for you! For this project, come up with a way to teach your agent to dig a tunnel down to around layer 10-13 underground, where diamonds are usually found. After you are at that level, you can dig parallel tunnels in search of diamonds, or even program the agent to do it for you. Mining with the agent is actually covered in Lesson 6: Conditionals, so you might even look ahead at that.

### ~ hint

In Minecraft, it’s generally not a great idea to dig straight down, because there are caverns underground and even if your agent does it, there isn’t always a place to put a ladder to climb back up. A stair-step approach is usually better, but you may still have to clean up after the agent in case it runs into a cavern where there aren’t any blocks, or if it runs into granite or sand, which can fall and obscure the stairs.

### ~

For this independent project, choose one of the following options. You can build any of these styles of staircases, but remember to use loops in your code to help do it.

## Staircase Project Options

### Option 1 - Straight Staircase

A straight staircase is most common, and it has the added benefit of allowing you to run up and down quickly if you line the rock with stairs.

![Different Stairs Options](/static/courses/csintro/iteration/stairs.png)

![Looking down the stairs](/static/courses/csintro/iteration/looking-down-stairs.jpg) Looking down the stairs

![Looking up the stairs](/static/courses/csintro/iteration/looking-up-stairs.jpg) Looking up stairs

This challenge is a little easier if you aren’t placing stairs, but there are a few things you should keep in mind.

1. You will need to jump up each level, and that increases the rate at which you need to eat. 
2. Also, it’s impractical to bring a horse down into the mine if you don’t have a wide, tall staircase lined with stairs. 

Perhaps you can work around these issues.

If you do decide to put down stairs...

1. By default, the agent places stairs facing backwards. This works well if you are building a staircase up, but if you are building a staircase down, think about how you could modify your code to make sure the stairs come out right.

2. If you try using the `||agent:agent place on move||` block, the agent will place a block every time it moves when this is set to `true`. You may need to toggle `||agent:agent place on move||` from `true` to `false` at certain points. Set it to `true` when you want to place stairs but `false` when you are just moving the agent and don't need to place anything.

Remember to use `||loops:LOOPS||` to reduce repetition of code!

After you have the agent building a straight set of stairs, consider how you might modify your code to create a staircase three blocks wide and with enough headroom to allow you to ride a horse down the stairs!

### Option 2 - Spiral Staircase

Another type of staircase is a spiral staircase. See if you can program the agent to dig this type of staircase for you.

![Dig spiral staircase, step 1](/static/courses/csintro/iteration/dig-spiral-1.jpg)

![Dig spiral staircase, step 2](/static/courses/csintro/iteration/dig-spiral-2.jpg)

![Dig spiral staircase, step 3](/static/courses/csintro/iteration/dig-spiral-3.jpg)

Start by digging one block, then two blocks, and then three blocks deep.

![Dig spiral staircase, step 4](/static/courses/csintro/iteration/dig-spiral-4.jpg)

After that, at each turn, remove a column of three blocks. You remove the block directly in front of the Agent (block 2 in picture) and the blocks directly above and below that (blocks 1 and 3 in the pictures).

![First 2 blocks to remove](/static/courses/csintro/iteration/proj-blocks.png)

![Dig spiral staircase, step 5](/static/courses/csintro/iteration/dig-spiral-5.jpg)

![Last Block to Remove](/static/courses/csintro/iteration/proj-blocks2.png)

![Dig spiral staircase, step 6](/static/courses/csintro/iteration/dig-spiral-6.jpg)

A spiral staircase involves much of the same code that you would use to create a straight one-block-wide staircase. Think about where you might have to turn. And, as in all the staircases, you will probably need to follow the agent to place torches and clean up falling granite.

### Option 3 - Diagonal Tunnel

One effective type of tunnel goes down at a diagonal angle. Can you create code that will get the agent to dig this type of tunnel? Digging a diagonal tunnel involves removing layers of blocks as shown.

#### Step 1: Remove the blocks indicated by granite.

![Diagonal tunnel, step 1](/static/courses/csintro/iteration/diagonal-tunnel-1.jpg)

#### Step 2: Remove the blocks indicated by diorite.

![Diagonal tunnel, step 1](/static/courses/csintro/iteration/diagonal-tunnel-1.jpg)

#### Step 3: Remove the center block.

![Diagonal tunnel, step 3](/static/courses/csintro/iteration/diagonal-tunnel-1.jpg)

#### Step 4: Continue in the same way, digging a diagonal tunnel.

![Diagonal tunnel, step 4](/static/courses/csintro/iteration/diagonal-tunnel-4.jpg)

#### Step 5: Tunnel is dug.

![Diagonal tunnel, step 5](/static/courses/csintro/iteration/diagonal-tunnel-5.jpg)

Note that the agent can’t face diagonally like you can, so you will need to figure out how to move the agent so that it can dig in the right direction. Is this even possible?

## Minecraft Diary

Compose a diary entry addressing the following:

* What type of staircase did you choose to build: Straight, Spiral, or Diagonal? Why?
* What problems did you encounter? How did you solve them?
* How did you use loops in your staircase? 
* Describe one point where you got stuck. Then discuss how you figured it out.
* Include at least one screenshot of your staircase.

## Assessment

**Competency scores**: 4, 3, 2, 1

### Diary

**4 =** Minecraft Diary addresses all prompts.  
**3 =** Minecraft Diary entry is missing one of the required prompts.  
**2 =** Minecraft Diary entry is missing two or three of the required prompts.  
**1 =** Minecraft Diary entry is missing four or more of the required prompts.

### 반복

**4 =** Uses loops effectively in a way that is integral to the program.   
**3 =** Uses loops in a way that is integral to the program, but there are some problems with loop output.  
**2 =** Uses loops effectively but in a superficial way.  
**1 =** Doesn’t use loops at all or uses loops in a superficial way and has problems with loop output.

### Project

**4 =** Staircase is complete and navigable in both directions. Ends at somewhere around layers 10-13.  
**3 =** Staircase lacks one of the required elements.  
**2 =** Staircase lacks two of the required elements.  
**1 =** Staircase lacks all of the required elements.