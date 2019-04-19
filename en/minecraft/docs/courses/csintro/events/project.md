# Independent Project

## ~ hint

**Teacher Note**

Open-ended, creative projects are opportunities to apply the concepts and skills students have developed to solve a problem or fill a need. In Minecraft, there are all sorts of problems to solve: How can you keep your cows from running away? How can you create a renewable water source? How can you get back to the surface after falling into a ravine? Projects allow kids to explore problems that are meaningful to them - and to use MakeCode to design original, automated solutions to many of the problems they face in their everyday Minecraft lives. It is important to give kids opportunities to create original projects to demonstrate that they can apply their MakeCode skills in new ways, and to exercise their creativity.

## ~

Remember that you learned in this lesson that events make things happen during the game. You will need to use event handler blocks to trigger different actions or results. In this project, your challenge is to come up with a simple MakeCode for Minecraft project that uses one or more of the following event handler blocks:

```blocks
player.onChat("jump", function () {

})
player.onDied(function () {

})
player.onTravelled(TravelMethod.Walk, function () {

})
player.onArrowShot(function () {

})
blocks.onBlockBroken(blocks.block(Block.Grass), function () {

})
blocks.onBlockPlaced(blocks.block(Block.Grass), function () {

})
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), function () {

})
mobs.onMobKilled(mobs.monster(MonsterMob.Creeper), function () {

})
```

Event Handler Blocks:

* `On chat command`
* `On player died`
* `On player walk/run/jump/swim/` etc.
* `On arrow shot`
* `On block broken`
* `On block placed`
* `On animal killed`
* `On monster killed`

For some of these blocks, you have many choices about the type of block, action, or animal affected.

## Sample Projects

### Kaleidoscope Build

![Kaleidoscope build](/static/courses/csintro/events/kaleidoscope-build.jpg)

In this project, every time you place a cobblestone block, three more are placed symmetrically relative to your location.

    ---------
    | X | O |
     -------
    | O | O |
    ---------   
    
    X = block placed
    O = new blocks
    

### Walk on Water

![walk on water](/static/courses/csintro/events/walk-on-water.jpg)

When you are crossing a lake or a river, make blocks of ice or glass appear under your feet so that you are literally walking on water.

### God of Weather

![god of weather](/static/courses/csintro/events/god-of-weather.jpg)

Create a chat command that makes it rain when it is clear or turn clear when it is raining.

### Spite

![spite](/static/courses/csintro/events/spite.jpg)

Create a command that, when it is active, spitefully kills everybody else when you die.

## Minecraft Diary

Compose a diary entry addressing the following:

* What problem did you solve, or why did you decide to create this project?
* What kind of event and event handler did you decide to use? 
* What does your program do? Describe how your program works (what the cause and effect are).
* Include at least one screenshot of your program working.
* Share your project to the web and include the URL here.

**NOTE:** If you decided to improve one of this lesson’s activities, please talk about the new code you wrote in addition to what was already provided in the lesson.

## Assessment

**Competency scores**: 4, 3, 2, 1

### Diary

**4 =** Minecraft Diary addresses all prompts.  
**3 =** Minecraft Diary entry is missing one of the required prompts.  
**2 =** Minecraft Diary entry is missing two or three of the required prompts.  
**1 =** Minecraft Diary entry is missing four or more of the required prompts.

### Project

**4 =** Project uses at least one event handler block AND causes an intentional effect or solves a problem.   
**3 =** Project uses at least one event handler block OR causes an intentional effect or solves a problem.  
**2 =** Project uses at least one event handler block OR causes an intentional effect or solves a problem BUT code is ineffective or flawed.  
**1 =** Project lacks all of the required elements.