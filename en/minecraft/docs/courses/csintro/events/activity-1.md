# Activity: Yellow Brick Road

## ~ hint

**Teacher Note**

A "birdhouse activity" is named after the birdhouses many of us made as our first projects in wood shop class. Everybody in class follows the same instructions to make the same thing. When everybody comes out with a birdhouse that looks halfway decent, you know they have all had at least an introduction to the concepts. These lessons first introduce the overall concepts in unplugged activities. Later, through coding activities, challenges, and experiments, students get a chance to practice the associated new coding skills. The lessons move from unplugged activities to "birdhouses" in preparation for more creative, open-ended projects after your students have demonstrated the skills at least once.

Don’t stop after the birdhouse! Although it is easiest to assess skills with the material in these lessons, be sure to give kids opportunities to apply the skills in even more open-ended challenges. Use these lessons as inspiration and a starting point, but the beauty of Minecraft and coding is creating - so have fun!

## ~

The `||player:on player walk||` block is an event handler that looks for a specific action by the player. Its drop-down menu lists all sorts of actions a player might perform, such as walking, jumping, attempting to swim in lava, and more.

![on player walk block](/static/courses/csintro/events/on-player-walk.jpg)

You can configure this event handler to cause something to happen when a player is walking. For example, you can leave flowers everywhere you walk!

## Do the activity

### Start by "listening" for the walk event

1. From the `||player:Player||` Toolbox drawer, drag the `||player:on player walk||` block into the coding Workspace.

![player toolbox drawer](/static/courses/csintro/events/player-drawer.jpg)

### Place some grass

1. From the `||blocks:Blocks||` Toolbox drawer, put the `||blocks:place at||` block inside the `||player:on player walk||` block until you hear and see it snap into place.

![block toolbox drawer](/static/courses/csintro/events/blocks-drawer.jpg)

### Place a flower

1. Using the drop-down menu in the `||blocks:place at||` block, select a `Dandelion` (yellow flower).

![block picker](/static/courses/csintro/events/block-pick.jpg)

### Walk around and grow flowers

Now, wherever you walk in the game, you will leave a trail of dandelions! Try it out in the game by pressing the `W` key on the keyboard to have your player walk forward in a Minecraft world. Then look behind you. You should see a trail of flowers!

### ~ hint

**Camera View**

Pressing `F5` on your keyboard changes the view so you can see the flowers appear as you walk around.

### ~

![player walking in world](/static/courses/csintro/events/walk-in-world.jpg)

### ~ hint

**Teacher Note**

The flowers are being placed at `(~0 ~0 ~0)`. We will explore the coordinate system in more detail in the next lesson. For now, it’s enough to know that the three coordinates (X, Y, Z) represent different directions in the Minecraft game:

* X coordinate - east / west
* Y coordinate - up / down
* Z coordinate - north / south 

The flowers in the previous example were placed at `(~0 ~0 ~0)`. The tilde (~) indicates that the coordinate is in relation to the character, so 0 blocks from the character.

### ~

### Try it with gold!

Because you used the coordinates `(~0 ~0 ~0)` in your `||blocks:place||` block, the flowers are being placed at the ground level. The `~0` in the middle, the Y coordinate, represents how far up or down the block will be placed.

Now suppose you want to leave a golden path behind you, so that a “yellow brick road” is created wherever you walk. You can do that with the same `||blocks:place at||` block. Just change from placing a flower to placing gold.

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    blocks.place(blocks.block(Block.GoldBlock), positions.create(0, 0, 0))
})
```

Watch what happens:

![place gold blocks](/static/courses/csintro/events/place-gold-blocks.jpg)

That's the right idea, but not exactly what you are going for. You are actually leaving a gold wall behind you, which is rather inconvenient. How might you sink those blocks into the ground so that they form a yellow brick road?

Let’s modify the **Y** coordinate by subtracting 1 so that the bottoms of the bricks are one level down.

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    blocks.place(blocks.block(Block.GoldBlock), positions.create(0, -1, 0))
})
```

Now let’s see what happens:

![gold blocks in a path](/static/courses/csintro/events/gold-blocks-path.jpg)

Much better! Try making it a proper yellow brick road, at least three bricks wide, so you and your friends can walk side by side. **Hint:** Use a different block from the `||blocks:Blocks||` menu!

**Solution:**

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    blocks.fill(
    blocks.block(Block.GoldBlock),
    positions.create(-1, -1, -1),
    positions.create(1, -1, 1),
    FillOperation.Replace
    )
})
```

### Coordinates and events

Now you have experimented a little with coordinates and events. The next lesson focuses more on coordinates **(X, Y, Z)**, but they were only briefly mentioned here. If you are a bit confused about coordinates at this point, do not worry!

## Challenges

Hopefully, events are becoming more clear. Try the following challenges to get more practice with events.

### Challenge 1 - Create a Diamond Ceiling

Use the yellow brick road example as a starting point.

How could you instead make a diamond ceiling when you walk? A ceiling might be nice in case it rains!

![diamond ceiling](/static/courses/csintro/events/diamond-ceiling.jpg)

### ~ hint

The middle coordinate (X, **Y**, Z) needs to change so you can place bricks above your head. Your character is two bricks high, but this starts at 0. Thus, your character's feet are at 0 and your character's head is at 1. Changing **Y** to 2 or 3 will put blocks right above your character's head.

### ~

![diamond ceiling coordinates](/static/courses/csintro/events/diamond-ceiling-coordinates.jpg)

### Challenge 2 - Build While Flying

As a challenge, place something when your character flies! The concept is similar to how you placed flowers and gold blocks before, but you will need to change a few things. Can you figure it out?

### ~ hint

Use these coordinates:

![walk through air](/static/courses/csintro/events/build-while-flying-challenge-coordinates.png)

### ~

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - Magic Carpet Ride

What if you built a magic carpet to support your movement around the world? This focuses on two events: `on player walk` and `on player fly`.

How could you change this code? Could you use other events? What else could you change?

### Experiment 2 - Magic Carpet Artistic Appeal

What if you built a magic carpet that changes between blocks based on the event? What other things might happen when you fly that could be different from when you are walking?