# Unplugged Activity: Walk Around the House

This activity works best with a partner. You will write instructions for your partner to walk completely around the outside of a Minecraft house and return to the start. You will need a chair and some way to write things down. Place the chair in the center of the room. The chair represents a Minecraft house. Your partner should stand next to one of the corners of the house.

Your goal is to write the instructions for your partner to walk all the way around the house, using these two commands:

    forward()
    turn left/right()
    

Your pseudocode will probably end up looking something like this:

    forward()
    turn left()
    forward()
    turn left()
    forward()
    turn left()
    forward()
    turn left()
    

Have your partner follow your algorithm to prove that it works.

Now notice that this is eight lines of code, and many of the lines repeat. In particular, the following two lines of code repeat four times:

    forward()
    turn left()
    

Programmers like to take shortcuts. A program that has fewer lines of code takes up less room in memory, and ultimately the shorter your program is, the easier it is to find mistakes. Whenever you have code that repeats, you have an opportunity to use a loop to simplify your code.

How could this be shortened? How about:

    Repeat 4 times:
        forward()
        turn left()
    

Go ahead and follow this revised code to prove that it works.

You have just rewritten eight lines of code as three lines of code by using a loop. The "repeat" command creates a loop. The code within the loop gets repeated a certain number of times, and then the program exits the loop.

## Types of loops in MakeCode

Computers use loops to repeat sets of instructions under different conditions. Here are some examples of loops you will find in MakeCode. See if you can think of some different types of activities that would be appropriate for each type of loop.

### Counted loops

#### Repeat *n* times

```blocks
player.onChat("repeat", function () {
    for (let i = 0; i < 4; i++) {

    }
})
```

#### For index 0 to *n*

```blocks
player.onChat("for", function () {
    for (let index = 0; index <= 4; index++) {

    }
})
```

Both `||loops:repeat||` and `||loops:for||` loops repeat ***n*** number of times. If you have 32 stairs in your house, going upstairs or downstairs would probably involve taking one step 32 times. Other examples of activities that repeat a set number of times include entering a building with double front doors, lacing your shoes, and turning the pages in a picture book.

Similar to a `||loops:repeat||` block, a `||loops:for||` block also performs its actions the number of times indicated, but it uses a variable called `index` that you can use inside the loop to check (although `index` is used by default, you can change this variable). If you need to do something on the fifth time through a loop, this might be a good loop for you!

### While (true) loops

```blocks
player.onChat("while", function () {
    while (true) {

    }
})
```

A `||loops:while||` loop runs as long as the condition inside of it is true. By default, true is always true, so in effect, a `||loops:while <true>||` loop runs forever. Usually, though, you replace the `<true>` with a condition that evaluates to `true` or `false`. For example, `while <hair is messy> brush hair` would continue to repeat brushing hair until `<hair is messy>` is false. Some examples of activities that might use a while loop include `while <soup remains> eat with spoon`; `while <energy greater than 0> do jumping jacks`; and `while <she hasn’t seen me> wave furiously`.

A `||loops:while||` loop is a good loop to use with an `if` statement inside. Look for this when we talk about conditionals.

```blocks
player.onChat("while", function (num1) {
    while (num1 < 10) {

    }
})
```

In Minecraft, you might have a `||loops:while||` block that repeats as long as the Agent detects redstone beneath it. You can think of a `||loops:while||` block as a `||loops:repeat||` block combined with a `||logic:if||` conditional statement – if there’s redstone beneath me, do these things....

### Forever loops

```blocks
loops.forever(function () {

})
```

A `||loops:forever||` loop starts running when the program starts and keeps going until the program ends. Some real-life examples are breathing or the beating of your heart.