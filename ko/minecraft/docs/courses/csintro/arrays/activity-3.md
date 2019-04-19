# Activity: Blocks by ID

You can store an assortment of blocks in an array and access them by ID however you like. The ID is a number Minecraft uses to keep track of all the items, blocks, and other things in the game. We’ll use the IDs for blocks and the power of arrays to store the information for us.

This project also features another block we have not tried up until this point.

```blocks
let myBlock = blocks.blockById(0)
```

This allows us to supply a number, the block ID, and it will return the block for us. You can experiment with different IDs but be aware that our own experiments led sometimes to fatal crashes. Even finding a list of IDs on the internet sometimes yielded the wrong IDs but this is what experimentation is about. Still, tread with a bit of caution.

## Do the activity

### Create the project

1. Create a new MakeCode project called "BlocksByID".

2. In the `||loops:LOOPS||` Drawer, there is an `||loops:on start||` block that will run its commands once, as soon as the project starts up. Drag that block into the coding Workspace.

3. From `||variables:VARIABLES||`, click the **Make a Variable** button.

4. Name this variable `Blocks`, and click **Ok**.

![Make the 'blocks' variable](/static/courses/csintro/arrays/makevariable.png)

### Make an array for block IDs

5. From `||variables:VARIABLES||`, drag `||variables:set||` into the `||loops:on start||`. Adjust the variable from **item** to **Blocks**.

6. Using the Search, type `Create Array`.

7. Drag a `||arrays:create array with||` into `||variables:set||`.

![Pick the create array block](/static/courses/csintro/arrays/createarray.png)

### Add blocks to the array

If you are feeling adventurous go to the javascript view and add five places in the array. It is a bit easier this way once you get past the code view! Each spot in the array will eventually be 1-5 as you will see later. Add the numbers 1-5 separated by commas. These five block IDs are:

**1** = stone, **2** = grass, **3** = dirt, **4** = cobblestone, and **5** = oak wood plank.

If you do use JavaScript, you can skip steps 8-11.

![Adding Array Spots Javascript](/static/courses/csintro/arrays/adding-array-spots-javascript.png)

8. Click the Plus **(+)** sign on `||arrays:create array with||` to add 4 more slots in your array so the total length of your array is 5.

9. From `||math:MATH||`, drag a `||math:number||` block into the first slot of the `||arrays:create array with||` block.

10. Populate the rest of your array with number blocks. Note – you can right-click on the `||math:number||` block and select Duplicate to make copies of this block, instead of dragging more blocks from the Toolbox.

![Empty Number Block](/static/courses/csintro/arrays/addingintegers.png)

```blocks
let Blocks: number[] = []
Blocks = [0, 0, 0, 0, 0]
```

### Pick your numbers

Create an assortment of 5 different types of blocks. Be aware that certain blocks will not mix well! For example, fire will burn all adjacent flammable blocks. This might be fun to play with or perhaps you want to make a design. The final project is about making art and this activity could be helpful with that so try out some different ideas.

11. Type the numbers to cycle through the first five block IDs: **1** = stone, **2** = grass, **3** = dirt, **4** = cobblestone, and **5** = oak wood plank. Again, you can search for a list of block IDs for the education edition or you could just try out different numbers from (1-252). For the most part you should be ok but again, do not be totally surprised if a fatal error occurs. Just restart. 

```blocks
let Blocks: number[] = []
Blocks = [1, 2, 3, 4, 5]

```

### A Loop to Print Out the Blocks

Now that we have our Block Array set up, let’s work on displaying the blocks in a `||loops:for||` loop.

12. From `||player:PLAYER||`, drag an `||player:on chat command||` block to the Workspace.

13. Rename the command "PrintBlocks".

14. From `||loops:LOOPS||`, drag a `||loops:for||` loop and place in `||player:on chat command "PrintBlocks"||`.

15. From `||math:MATH||`, drag a `||math:subtraction||` block out to replace the default number 4. We will subtract 1 from the length of the array.

The reason you are using a `||loops:for||` loop here is to see another way you might cycle through your loops and get the information. Recall in previous activities this loop was used:

```block
let warp_array: number[] = []
for (let value of warp_array) {

}
```

This other `||loops:LOOP||` is great! In fact, you might rewrite this code and try to use the `||loops:for element of ||` to do the same thing we are accomplishing here in this activity. This could be a personal challenge. However, you can learn more and try out more of the array blocks if we try different ways of accomplishing our goal.

Your code should now look something like:

```blocks
let Blocks: number[] = []
player.onChat("PrintBlocks", function () {
    for (let index = 0; index <= 0 - 0; index++) {

    }
})
Blocks = [1, 2, 3, 4, 5]
```

16. Search for `||arrays:length of array||`. This returns the number of values in an array. Place this in the first slot of your `||math:subtraction||`.

17. Add `||variables:Blocks||` into `||arrays:length of array||`.

18. Add a 1 into the second slot of your `||math:subtraction||`.

Your code should look similar to this:

```blocks
let Blocks: number[] = []
player.onChat("PrintBlocks", function () {
    for (let index = 0; index <= Blocks.length - 1; index++) {

    }
})
Blocks = [1, 2, 3, 4, 5]
```

What is this doing?

When examining long pieces of code, it is important to cut things down into smaller chunks. If it helps use paper and pencil to keep track of the logic.

Here we can see:

1. We are getting the length of our array which will be 5.

2. We subtract 1. This means the loop will now go from 0 to **4**, (5-1).

3. Index becomes important. This is what we will use as the index or key for our array because now the numbers will align perfectly.

![Explaining this Loop](/static/courses/csintro/arrays/act3-explain-loop.png)

It is a bit more work than this loop:

```block
let warp_array: number[] = []
for (let value of warp_array) {

}
```

But by doing it this way, you could have multiple arrays that use the same key. In one of the experiments below the code does just that!

### Print Blocks by IDs

19. From `||blocks:BLOCKS||`, drag a `||blocks:place||` into the `||loops:for||` loop.

20. Again, from `||blocks:BLOCKS||`, drag a `||blocks:block by ID||` out to replace the default grass block in `||blocks:place||`.

21. From `||arrays:ARRAYS||`, drag a `||arrays:get value at||` and place it inside `||blocks:block by ID||`.

`||arrays:get value at||` will look in our `||variables:Blocks||` array and get our IDs(1-5) according to the key we feed it. So we have to adjust this just a bit more to get what we want. However, if you supply 0 for example we want it to give us the ID of 1.

22. Adjust `||arrays:get value at||` so it reads `||arrays:"Blocks" get value at "index"||`. You can get the variable `||variables:Index||` from the `||variables:VARIABLES||` drawer.

```block
let index = 0
let Blocks: number[] = []
blocks.place(blocks.blockById(Blocks[index]), positions.create(0, 0, 0))
```

24. In the position parameters for `||blocks:place||`, set the XYZ coordinates as (~2, ~0, ~index). Drag `||variables:Index||` and place it as the **Z** coordinate.

Your code should look similar to this:

### Completed Code

```blocks
let Blocks: number[] = []
player.onChat("PrintBlocks", function () {
    for (let index = 0; index <= Blocks.length - 1; index++) {
        blocks.place(blocks.blockById(Blocks[index]), positions.create(2, 0, index))
    }
})
Blocks = [1, 2, 3, 4, 5]
```

### Try the *"PrintBlocks"* command

Open up a Flat World in the Minecraft game, and type "PrintBlocks" in the chat window. You should see the blocks being built! You can add to the array to print more blocks or change the numbers from 1-5 to any numbers between 1 and 252. Again, this is an estimation and things do change so be aware that if something goes terribly wrong, you should just not use that ID anymore!!!

![Complete Array program](/static/courses/csintro/arrays/blockids.png)

### Challenge 1 - Randomly Print One of the Stored Blocks

Can you randomly print a block out of the array? You would need to build a variable called `RandomBlock`.

![Complete Array program](/static/courses/csintro/arrays/act3-ch1.png)

In that variable you would select a number randomly from 0 to the length of the array - 1. Remember we subtract 1 because arrays are zero based. There are other ways to work around this too if you want to try.

The solution posted here picks a random block from the array. It prints 5 blocks but you could print more if you wanted, right? How?

Some blocks might be printed twice because they are chosen randomly.

![Printing a Random Block](/static/courses/csintro/arrays/blockidsrandom.png)

### Challenge 2 - Remove a block and report feedback

Thus far we have only added things to arrays but you can also delete items. Using:

```block
let list: number[] = []
let item = 0
item = list.removeAt(0)
```

`||arrays:remove value at||` will delete 1 item from your array. You just tell it the key or index where you want to delete it.

Can you print your blocks and then after each printing, delete the last item in the array? You should report your action to the user so they understand what happened. The beginning of this is posted in the picture. Try to fill in the rest.

![Complete Array program](/static/courses/csintro/arrays/act3-ch2.png)

![Remove from Array](/static/courses/csintro/arrays/act2-finished.jpg)

### Experiment 1 - Print Blocks and Names... Two Arrays in Parallel

This prints the blocks in an array but there is a second array which holds the names of the blocks. By saying in parallel, it means the arrays have connected keys or indexes.

예를 들어:

```typescript-ignore
Blocks[1] = [159]
BlockNames[1] = ["Terracotta"]
```

These two pieces of information are talking about the same thing. One array stores the ID and the other stores the name but they both have the same key. Having the same index makes it a lot easier to get to all the information at one time if we want to.

In theory you could make several arrays in parallel to store multiple pieces of information.

For example, maybe you wanted to create profiles for your monsters. Consider four arrays in parallel.

```typescript-ignore
Name[1] = ["Bob"]
FavoriteFood[1] = ["pizza"]
FavoriteColor[1] = ["red"]
Age[1] = [25]
```

Here by using the key of 1 you could get multiple pieces of information stored about just one monster.

![Two parallel arrays](/static/courses/csintro/arrays/twoparrallelarrays.png)

### Experiment 2 - Print with Data Values

Some blocks or items from the game have a data value. The data value is used to print the same object but the style or color may vary depending on the data value. Think of it like having the same kind of car but with different options.

For instance, there are 16 types of concrete listed. All have the ID of 251 but each has a different data value (0-15, 16 total) to indicate a different color.

This code prints blocks from arrays but using the `DataValue` array to determine the style.

Because we use a for loop here we are able to access three different types of information about the same block, all with the same key!

This is very dangerous and the listings for data values did not seem accurate at the time of this publication. Again, experiment if you want to but be wary. It might be best to first find blocks by ID and then experiment by playing with data values. This would be the safest way to avoid a game ending error.

![Using Data Values to Print Blocks](/static/courses/csintro/arrays/act-exp2.jpg)