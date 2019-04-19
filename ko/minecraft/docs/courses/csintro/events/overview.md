# Events

An *event* in computer science is an action or occurrence that is detected by a computer. For example, when someone clicks the button on their mouse, it generates a “mouse click event” for the computer. In real life, there are also events that might be associated with an action, like cause and effect. Here are some examples:

| Event | Action | | - | - | | It starts raining | People open umbrellas | | The bell rings | Students go to class | | The power button is pressed | The computer turns on | | The mouse button is clicked | An application opens |   


Can you think of some other events and what they might cause to happen?

In programming, an *event handler* is a part of your program that runs when a specific event happens (it “handles” the event). In MakeCode, an event handler block looks like a square with a gap in the middle and usually starts with the word “on”:

```blocks
player.onTravelled(TravelMethod.Walk, function () {

})
blocks.onBlockPlaced(blocks.block(Block.Grass), function () {

})
mobs.onMobKilled(mobs.animal(AnimalMob.Chicken), function () {

})
player.onChat("jump", function () {

})
```