# Paired independent project: Build an AI

For an independent project, now it’s your turn to work with another student to teach the Agent or the Builder to intelligently adapt to the Minecraft environment. You can use conditional statements to allow the Agent or the Builder to evaluate its environment and make its own decisions accordingly.

For certain tasks, you may want to use the Builder instead of the Agent because the Builder is faster and can save its current position. However, the Builder is also invisible, so it can be difficult to see exactly what it is doing while it is working.

## Pair brainstorm

First, sit with your partner and brainstorm about five or six common tasks in Minecraft that might be automated. Here are some ideas as a starting point:

* Finding temples
* Finding villages
* Finding dungeons
* Harvesting mature wheat
* Harvesting tall sugar canes
* Finding the way out of a cave
* Building a road but navigating the landscape

You and your partner should pick two different tasks from your list that would require the Agent or the Builder to evaluate its environment and react differently. Try to write out, in pseudocode, what the steps would be to accomplish each task.

## An example and pseudocode

Here is one example, for finding jungle temples. The Builder will fly over the treetops and examine a given search area beneath the tree line until it finds moss stone above ground, which is likely to be the site of a jungle temple. This is similar to the tree cover-penetrating radar that archaeologists use to find real temples in the Amazon!

    Create a variable for steps
    Create a variable for turns
    Teleport the Builder to my position
    Ascend to 20 blocks above my position
    
    While a test for moss stone in an area between 20 and 15 blocks below the Builder is negative:
        Change the number of steps by 1
        If the number of steps is greater than the search area:
            Alternate turning right or left based on the value of turns
            Reset steps to zero
            Flip the value of turns (i.e., if it’s true, make it false, and vice versa.)    
        Move forward to search a new area
    
    If you have found moss stone,
        report your current position since moss stone above ground level is the likely spot of a jungle temple.
    

You can use a similar algorithm for finding strongholds or dungeons. It is a good idea to have the Builder report its position every so often (using a `||player:say||` block) so you have an idea of where it is and what it is doing.

As a pair, decide which one of these tasks seems the most promising, and then go ahead and build it in MakeCode. Be sure to test it out and make adjustments as necessary!

## Minecraft Diary

Compose a diary entry addressing the following:

* What Minecraft problem did you decide to solve? What does your program do?
* Describe how your AI figures out how to perform the task or solve the problem
* Discuss one (or more) ways that working with a partner was different from just doing the project by yourself.
* Describe one point where you got stuck. Then discuss how you figured it out.

**NOTE:** If you decided to improve one of this lesson’s activities, please talk about the new code you wrote in addition to what was already provided in the lesson.

## Assessment

**Competency scores**: 4, 3, 2, 1

### Diary

**4 =** Minecraft Diary addresses all prompts.  
**3 =** Minecraft Diary entry is missing 1 of the required prompts.  
**2 =** Minecraft Diary entry is missing 2 or 3 of the required prompts.  
**1 =** Minecraft Diary entry is missing 4 or more of the required prompts.

### 논리

**4 =** Agent and/or Builder completes its assigned task in all circumstances all the time.  
**3 =** Agent and/or Builder completes its assigned task most of the time in most situations.  
**2 =** Agent and/or Builder completes its assigned task some of the time and in some situations.  
**1 =** Agent and/or Builder never completes its assigned task.

### Project

**4 =** Project solves a specific problem, efficiently and effectively.  
**3 =** Project solves a specific problem mostly efficiently.  
**2 =** Project solves a specific problem but execution of the task is cumbersome or inefficient.  
**1 =** Project code is greatly cumbersome and inefficient.