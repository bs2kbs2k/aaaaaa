# Activity: Burger

Create a tribute to a very popular food, the burger. This program uses functions to create a mouth-watering creation with a few ingredients.

This is the perfect example for functions. Functions allow you to divide your big projects of code into smaller more manageable pieces. The construction of a burger can also be divided in such a way.

Your burger code will have five parts:

1. Creating the Bottom Bun
2. Creating the meat
3. Creating the lettuce
4. Creating the tomato
5. Creating the Top Bun

## Do the activity

### Make a function

1. Create a new MakeCode project called **burger**.

2. Click the Advanced tab on the Toolbox to display more Toolbox categories.

3. In `||functions:FUNCTIONS||`, click the **Make a Function** button.

![Make a Function](/static/courses/csintro/functions/make-a-function.png)

### Name the function

4. Name this function *bottomBun()*, and click **Ok**.

### Make the *meat()*, *lettuce()*, *tomato()*, *topBun()* functions

5. Repeat the previous step to create four more functions named `meat`, `lettuce`, `tomato`, and `Top Bun`.

6. From `||player:PLAYER||`, drag a `||player:on chat command||` block onto the Workspace.

7. Rename this `||player:on chat command||` to `"burger"`.

8. From `||functions:FUNCTIONS||`, drag the five blocks `||functions:call function bottomBun||`, `||functions:call function meat||`, `||functions:call function lettuce||` , `||functions:call function tomato||`, and `||functions:call function topBun||` into `||player:on chat command "burger"||`.

**NOTE:** The order of these function calls is important.

```blocks
function lettuce()  {

}
function bottomBun()  {

}
function topBun()  {

}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function meat()  {

}
function tomato()  {

}
```

`||player:on chat command "burger"||` will be your main program to start your burger build. Now, you just need to fill in the individual functions.

### Create the bottom bun

The first thing you’ll do is create the bottom bun.

9. From `||blocks:BLOCKS||`, drag a `||blocks:fill||` into `||functions:bottomBun||`. Change the block by clicking **Oak Wood Planks** from the drop-down menu.

10. Enter the coordinates for the top bun with a starting position of `(~3, ~0, ~3)` and ending position of `(~8, ~0, ~8)`.

```blocks
function bottomBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 0, 3),
    positions.create(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {

}
function tomato() {

}

```

![Bottom Bun for burger](/static/courses/csintro/functions/bottombun.jpg)

Doesn't look like much yet!

### "Cook" the meat

Let's create a layer of meat.

11. From `||blocks:BLOCKS||`, drag a `||blocks:fill||` into `||functions:meat||`.

12. Adjust the material by selecting **Brown Terracotta** from the drop-down menu. Then change the position in the coordinates section to a starting position of `(~4, ~1, ~4)` and a finishing position of `(~7, ~1, ~7)`.

## ~ hint

**Duplicate**

Remember that you can also duplicate blocks by right-clicking and selecting **Duplicate**. Then you just make adjustments.

## ~

```blocks
function bottomBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 0, 3),
    positions.create(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {

}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {
    blocks.fill(
    blocks.block(Block.BrownTerracotta),
    positions.create(4, 1, 4),
    positions.create(7, 1, 7),
    FillOperation.Replace
    )
}
function tomato() {

}

```

![meat for burger](/static/courses/csintro/functions/meat.jpg)

### Create the lettuce

Let's create a layer of lettuce.

13. From `||blocks:BLOCKS||`, drag a `||blocks:fill||` into the `||functions:lettuce||` function.

14. Change the material selecting **Lime Concrete** from the drop-down menu. Then change the position in the coordinates to a starting position of `(~4, ~2, ~4)` and a finishing position of `(~7, ~2, ~7)`.

```blocks
function bottomBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 0, 3),
    positions.create(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
     blocks.fill(
    blocks.block(Block.LimeConcrete),
    positions.create(4, 2, 4),
    positions.create(7, 2, 7),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {
    blocks.fill(
    blocks.block(Block.BrownTerracotta),
    positions.create(4, 1, 4),
    positions.create(7, 1, 7),
    FillOperation.Replace
    )
}
function tomato() {

}

```

![lettuce for burger](/static/courses/csintro/functions/lettuce.jpg)

### Create the tomato

Let's create a layer of tomato.

15. From `||blocks:BLOCKS||`, drag a `||blocks:fill||` into the `||functions:tomato||` function.

16. Change the block by selecting **Red Concrete** from the drop-down menu. Then change the position in the coordinates to a starting position of `(~4, ~3, ~4)` and a finishing position of `(~7, ~3, ~7)`.

```blocks
function tomato() {
    blocks.fill(
    blocks.block(Block.RedConcrete),
    positions.create(4, 3, 4),
    positions.create(7, 3, 7),
    FillOperation.Replace
    )
}
tomato()
```

![tomato for burger](/static/courses/csintro/functions/tomato.jpg)

### Create the top bun

The finally function is the top bun. To give the burger a more realistic look, this function will fill in two layers instead of just one.

17. From `||blocks:BLOCKS||`, drag two `||blocks:fill||` blocks into the `||functions:topBun||` function.

18. Change the material for each fill to **Oak Wood Planks**.

19. Change the top fill coordinates first. The position for the coordinates should have a starting position of `(~3, ~4, ~3)` and a finishing position of `(~8, ~4, ~8)`.

20. The bottom fill should have a starting position of `(~4, ~5, ~4)` and a finishing position of `(~7, ~5, ~7)`.

```blocks
function topBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 4, 3),
    positions.create(8, 4, 8),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(4, 5, 4),
    positions.create(7, 5, 7),
    FillOperation.Replace
    )
}
topBun()
```

## The completed code

```blocks
function meat() {
    blocks.fill(
    blocks.block(Block.BrownTerracotta),
    positions.create(4, 1, 4),
    positions.create(7, 1, 7),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 4, 3),
    positions.create(8, 4, 8),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(4, 5, 4),
    positions.create(7, 5, 7),
    FillOperation.Replace
    )
}
function tomato() {
    blocks.fill(
    blocks.block(Block.RedConcrete),
    positions.create(4, 3, 4),
    positions.create(7, 3, 7),
    FillOperation.Replace
    )
}
function bottomBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 0, 3),
    positions.create(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
    blocks.fill(
    blocks.block(Block.LimeConcrete),
    positions.create(4, 2, 4),
    positions.create(7, 2, 7),
    FillOperation.Replace
    )
}
```

![Completed burger](/static/courses/csintro/functions/burger.jpg)

![Completed burger zoomed out](/static/courses/csintro/functions/burgerzoomout.jpg)

## Challenges

Let's add more to the burger!

### Challenge 1 - burger Plate

You should create a plate for the burger. To do this, include another function and name it **plate**. Don't forget to add a call to the plate function in `||player:on chat command "burger"||`.

### Challenge 2 - Circular lettuce

Can you use the circle block to create more realistic lettuce?

![Search for Circle](/static/courses/csintro/functions/act3-challenge2.png)

## Experiments

Let's change some things to make our own different and unique situations!

### Experiment 1 - Bat Cave

This code uses three functions. One function digs a cave. Another delays the code to give you a change to fly away because the last function creates a whole lot of bats!

Add something fun to this. Can you think of an enhancement?

## ~ hint

**Stand on the Ground**

For the `||functions:cave||` function to work properly, you need to be standing on the ground when you start the code.

## ~