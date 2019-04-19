# Functions

Often in programming, there are tasks or procedures that are used frequently within the same program. In [Lesson 5 - Iteration](/courses/csintro/iteration), you tried one way you can repeat actions by using loops. Functions allow you to repeat code too but are a bit more powerful for organizational purposes.

Loops will repeat the code inside them for the number of times you ask. Functions run the code inside them only once, but their power is that they can allow you to reuse code anywhere you want. You can write the set of instructions once as a function and from then on simply "call" the function from inside your program whenever you need that task done. This is great because you need to edit in only one place if you need changes in the future. Also, your code will be easier to read. Consider the following two examples. Which one would you rather edit?

```blocks
player.onChat("run", function () {
    for (let i = 0; i < 4; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
        blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0))
    }
    for (let i = 0; i < 4; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
        blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0))
    }
    for (let i = 0; i < 4; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
        blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0))
    }
    for (let i = 0; i < 4; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
        blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0))
    }
    for (let i = 0; i < 4; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
        blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0))
    }
})
```

```blocks
player.onChat("run", function () {
    OnlyEditOnce()
    OnlyEditOnce()
    OnlyEditOnce()
    OnlyEditOnce()
    OnlyEditOnce()
})
function OnlyEditOnce() {
    for (let i = 0; i < 4; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
        blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0))
    }
}
```

Both of the preceding examples do the same thing. The difference is when you use functions, you only need to edit things once. If you want to change coordinates, for example, or an animal you are spawning, you just make one change! Without functions, you would need to make five changes. This makes testing and debugging a lot easier.

Grouping frequently used instructions into a function makes your code more efficient but also makes it easier to understand. Functions help you organize your code so that it fits the problem you are coding for. A function is usually given a name that describes the task it will perform when called, making your code easier to read. You are able to divide up problems into smaller, more manageable pieces.

Let's suppose you want to make code that drives a car. Using functions, you would make one function for each part of driving. You can think about your overall goal and use functions to help you plan. To drive, you need to turn on the car, sit, stop, open the door, and do various other things like this. Each of these would be a function.

```blocks
function OpenDoor()  {

}
player.onChat("DriveCar", function () {
    OpenDoor()
    SitDown()
    TurnOnEngine()
    ApplyBrake()
    PutInDrive()
    ApplyBrake()
    OpenSunRoof()
})
function SitDown()  {

}
function TurnOnEngine()  {

}
function ApplyBrake()  {

}
function PutInDrive()  {

}
function OpenSunRoof()  {

}
```

## Example: Writing Your Name

Consider this example: As a student, you are probably asked several times a day to write your name on a paper, a form, or a sign-up sheet. Writing your name is a function that you do without thinking about it very much, yet the task is actually made up of a number of smaller steps. Let’s take a look at what those steps would be for a person named *Mary*.

The function could be called **WriteMyName**.

The list of steps or lines of code performed when **WriteMyName** is called for Mary would be:

1. Write a capital **M**.
2. Just to the right of the previous letter, write a lowercase **a**.
3. Just to the right of the previous letter, write a lowercase **r**.
4. Just to the right of the previous letter, write a lowercase **y**.

Whenever Mary needs to write her name, she calls the function **WriteMyName**, and that set of instructions is carried out.

![WriteMyName Pseudocode Example](/static/courses/csintro/functions/overview-mary-example.png)