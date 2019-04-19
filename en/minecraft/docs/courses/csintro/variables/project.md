# Independent Project

In this lesson, you’ve looked at how to create a new variable and how to change the value of an existing variable. You learned how to pass the value of a variable into the `on chat command` block as a parameter, and you also looked at one way to use a variable to keep track of events that happen in the game.

For this project, create an original MakeCode project that uses multiple variables of at least two different types, to keep track of information in Minecraft. Also, find a way to use a chat command with a parameter (this can be in the same project or in a different project).

## Information you might store in variables / project ideas

* Store the number of something you spawn (*5* if you spawned five parrots).
* Store text for the animal you spawned (*cow* if you spawned cows).
* Store your position (*(3, 5, 7)* if you saved your current world position).
* Store a relative position (*(2, 30, 100)* if you calculated the relative position of your house from where you currently are in the world. This would be similar to your GPS telling you, "You will be home in 10 minutes!")
* Store words to put together to make sentences.

## Example - Alpine Ski Race

Take turns jumping up a mountain. Keep track of the elapsed time, as well as the number of jumps it took each person from start to finish. Here is some starter code that you can use to do the timing.

```blocks
let current = 0
let old = 0
player.onChat("time", function () {
    current = gameplay.timeQuery(TimeQuery.GameTime)
    player.say("Time: " + (current - (old + 20)) + " secs")
    old = current
})
```

This code creates two variables, one to hold the current game time in ticks, and the other to hold the old value. When you enter **time** in the chat window, the code will display the number of seconds that have elapsed since the last time you called **time**.

To time a race, enter **time**, start racing, and then when the race finishes, enter **time** again.

## Minecraft Diary

Compose a diary entry addressing the following:

* What type of information did you choose to keep track of?
* What problems did you encounter? How did you solve them?
* How did you use variables in your project, and what were their types? 
* What did you name your variables and why?
* What was something new that you learned for this project? Describe how you figured it out.
* Include at least one screenshot of your project.

**NOTE:** If you decided to improve one of this lesson’s activities, please talk about the new code you wrote in addition to what was already provided in the lesson.

## Assessment

**Competency scores**: 4, 3, 2, 1

### Diary

**4 =** Minecraft Diary addresses all prompts.  
**3 =** Minecraft Diary entry is missing one of the required prompts.  
**2 =** Minecraft Diary entry is missing two or three of the required prompts.  
**1 =** Minecraft Diary entry is missing four or more of the required prompts.

### Variables

**4 =** At least three different variables are implemented in a meaningful way. Variables are of different types (text, number, Boolean, and/or position).  
**3 =** At least two different variables are implemented in a meaningful way. Variables are of different types (text, number, Boolean, and/or position).  
**2 =** At least one variable is implemented in a meaningful way OR variables are all of the same type.  
**1 =** No variables are implemented.

### Chat / parameter

**4 =** Project incorporates a chat command that uses one or more parameters in the enclosing code.   
**3 =** Project uses a chat command with one or more parameters that are not used by the code.  
**2 =** Project uses a chat command but does not implement parameters.  
**1 =** Project uses no chat command at all.