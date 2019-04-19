# 지역 함수

Challenge the student to use code in Minecraft to make similar quadrilaterals previously drawn by hand.

## Learning objectives

Play with a function for the area of a quadrilateral to gain understanding of how its width and height relate to the number of blocks within the entire area of the shape.

## ~ hint

#### Applicability

**Skill areas**: Math, Area, Functions, Shapes

**Ages**: 7-9 yrs old

**Grade level**: 3rd

## ~

## Guiding ideas

Understanding the relationship between the width and height of a shape and the number of blocks that create the solid shape is difficult for third grade students. This challenge assists in comprehension of dimensional area by demonstrating the change in area with a change in side dimensions.

#### Related Common Core math standards:

* [CCSS.MATH.CONTENT.3.MD.C.6](http://www.corestandards.org/Math/Content/3/MD/#CCSS.Math.Content.3.MD.C.6)
* [CCSS.MATH.CONTENT.3.MD.C.7](http://www.corestandards.org/Math/Content/3/MD/#CCSS.Math.Content.3.MD.C.7)

## 학생 학습 활동

This activity requires students to have the *Code Connection* app open and running with their *Minecraft Education Edition*.

이 활동은 2개의 부분으로 이루어져 있습니다.:

* [Creating quadrilaterals on paper and in game](#creating-quadrilaterals)
* [Creating quadrilaterals with code](#coding-quadrilaterals)

### Creating quadrilaterals on paper and in game

Lead a class discussion on quadrilaterals, specifically calling out that they always have 4 sides. It is recommended that students focus on squares and rectangles for this activity, but the activity can extend to making parallelograms for advanced coders.

Using the [Area Worksheet](/lessons/area/worksheet), have each student draw their individual shape using blocks, and calculate the area using width and height. Then lead a discussion with the entire class, showing examples of different student’s worksheets and how there is a relationship between adding the number of rows over and over and multiplying the rows by the columns.

Then, in the Minecraft game, have each student choose a Minecraft material (such as gold) and build a 3-dimensional quadrilateral as a wall. To start, each student should be given a number between 15 and 30 and are allowed to make a quadrilateral with only that number of blocks.

![Area Wall](/static/lessons/Area-16block.png)

### Creating quadrilaterals with code

After students have completed the [Area Worksheet](/lessons/area/worksheet) and manually built their shapes in Minecraft, lead a discussion on the area formula and have students play with the program below that will create their shape AND report the area. Copy and paste this URL in the Projects dialog to open this program in MakeCode: <https://makecode.com/_FccCsk7em5ec>. Then from the Minecraft game, press 't' to open the chat window and type in 'area' with a width and height value. Have students test out different width and height values for their shapes. Try pressing the Snail icon in the bottom left corner of the MakeCode screen to run this code in 'Slo-Mo' to see how it builds the shape with the correct number of rows and columns.

#### Completed solution

```blocks
let y = 0
let x = 0
let height = 0
let width = 0
player.onChat("area", function (width, height) {
    player.say("Making a shape with a width of: " + width + " and a height of: " + height)
    for (let x = 0; x <= width; x++) {
        for (let y = 0; y <= height; y++) {
            blocks.place(blocks.block(Block.GoldBlock), positions.create(x, y, 0))
        }
    }
    player.say("The total number of blocks used was: " + height * width)
})
```

## Performance expectations

#### Intended outcomes:

* Allowing a class period to build and share quadrilateral shapes within Minecraft to understand how the height and width change the area.
* Allowing a class period to discover the formula for area and then to compare and contrast quadrilaterals based on the formula and the shapes within Minecraft.

## 자료

[Area Worksheet](/lessons/area/worksheet), [Area Cheatsheet](/lessons/area/cheatsheet)