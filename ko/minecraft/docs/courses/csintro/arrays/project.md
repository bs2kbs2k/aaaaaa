# Independent Project

## Arrays for art

For this chapter’s independent project, use an array to create a piece of artwork. For inspiration, take a look at the project called [Rainbow Beacon](/examples/rainbow-beacon) in the [Super Powers](/examples/super-powers) category in Code Connection. This project loads an array with colored wool, and then shoots it straight up toward the sky, as far as the eye can see.

![Rainbow colored tower of blocks](/static/courses/csintro/arrays/rainbow-tower.jpg)

How might you modify this project? Could you make a rainbow road stretching out to the horizon? Or create a flat square with a rainbow design? What about a rainbow house or tower? With arrays and loops, you have the power to create enormous public artwork that stretches out, and up, in different dimensions. See what kind of colorful, multi-dimensional artwork you can create!

### Ideas

Some ideas for array art:

* Create designs and patterns by placing various types of decorated sandstone from an array.
* Create a maze of random blocks.
* Design intricate patterns in the ground so flying above them becomes fun.
* Create a pattern by using an array of only black and white wool blocks.
* Create a bar graph by dropping various amounts of sand from the sky based on the numbers in an array. The dropping would be interesting to watch! ![Sand block bar graph](/static/courses/csintro/arrays/sand-block-bargraph.jpg)
* Water creates some cool effects when placed outside a container. ![water art](/static/courses/csintro/arrays/project-ideas.jpg)
* Lava and fire are also interesting to work with.
* Don't forget you can erase blocks by filling them with air.

### Project criteria

Your project should do the following:

* Use an array of items.
* Access items in the array either in sequence or at random.
* Only access indexes that exist in the array (prevent "out-of-bounds" access).

### ~ hint

**"out-of-bounds" access**

This means that it is possible to give an index that would cause an error.

For example, maybe my array has two items in it.

```typescript-ignore
item1 = myitems[0]
item2 = myitems[1]
```

If a user tried to access

```typescript-ignore
myitems[4]
```

it would cause an "out-of-bounds" access error.

### ~

### ~ hint

**"out-of-bounds" prevention**

`||logic:if then else||` statements are a great way to check and prevent this kind of error.

### ~

## Minecraft Diary

Compose a diary entry addressing the following:

* What kind of art did you decide to make? What does your program do?
* Describe how your program creates its artwork.
* How did you ensure that only valid indexes are accessed?

**NOTE:** If you decided to improve one of this lesson’s activities, please talk about the new code you wrote in addition to what was already provided in the lesson.

## Assessment

**Competency scores**: 4, 3, 2, 1

### Diary

**4 =** Minecraft Diary addresses all prompts.  
**3 =** Minecraft Diary entry is missing 1 of the required prompts.  
**2 =** Minecraft Diary entry is missing 2 or 3 of the required prompts.  
**1 =** Minecraft Diary entry is missing 4 or more of the required prompts.

### Project

**Required**

* Use an array of items.
* Access items in the array either in sequence or at random.
* Only access indexes that exist in the array (prevent "out-of-bounds" access).

**4 =** Project creates a piece of artwork, efficiently and effectively.  
**3 =** Project is missing 1 of the required elements.  
**2 =** Project is missing 2 of the required elements.  
**1 =** Project lacks all of the required elements.

### 배열

**4 =** Array is properly created, possible to access all elements, no out-of-bounds access.  
**3 =** Array is properly created, (possible to access all elements or no out-of bounds access)  
**2 =** Array is properly created, some elements not reachable, and out-of-bounds access not prevented.  
**1 =** Array is not created properly or used at all, no means of stopping out-of-bounds access was implemented.