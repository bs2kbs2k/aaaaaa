# Activity: Sing a Song of Sixpence

> *“Sing a song of sixpence,* _A pocket full of rye._  
> _Four and twenty blackbirds,_  
> _Baked in a pie.”_  
> – English Nursery Rhyme

In this activity, students will take inspiration from an old English nursery rhyme, because old English nursery rhymes are super popular with young people these days. Right?

You will change it up just a little, though. Instead of blackbirds you will use parrots, and instead of pie you will use cake!

## Do the activity

### Check for broken blocks

1. From `||blocks:Blocks||`, drag `||blocks:on broken||` onto the coding Workspace. This will be your event handler.

```blocks
blocks.onBlockBroken(blocks.block(Block.Grass), function () {

})
```

### Go for the cake

2. Using the drop-down menu, select the `Cake` item. Use that friendly search!

![the searchbar is your friend](/static/courses/csintro/events/cake-searchbar-is-your-friend.png)

### Spawn an animal

3. From `||mobs:Mobs||`, place `||mobs:spawn animal||` under the `||blocks:on broken||` block until you hear it snap into place.

```blocks
blocks.onBlockBroken(blocks.block(Block.Cake), function () {
    mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 0, 0))
})
```

### Make it a parrot

4. From the drop-down menu in the `||mobs:spawn animal||` block, select a `parrot`.
5. You want to spawn the parrots above your head, so in the `||mobs:spawn animal||` block, change the **Y** coordinate to **1**.

![pick the parrot mob](/static/courses/csintro/events/pick-parrot-mob.jpg)

### More parrots!

This will spawn only one parrot above your head, so let’s use a `||loops:repeat||` loop to spawn 24 parrots.

6. From `||loops:loops||`, place a `||loops:repeat||` loop around `||mobs:spawn animal||`.

7. In the `||loops:repeat||` loop, enter the number **24**.

```blocks
blocks.onBlockBroken(blocks.block(Block.Cake), function () {
    for (let i = 0; i < 24; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Parrot), positions.create(0, 1, 0))
    }
})
```

### Run the code

To run this in the game, add a cake to your player inventory (press `E` to open your inventory), select the cake in your toolbar (use the mouse wheel or the number keys), and right-click to place the cake on the ground.

Then change back to your hands and use the left mouse button to hit the cake to destroy it – you should see a flock of parrots appear!

![parrots appear around the cake](/static/courses/csintro/events/parrots-appear.jpg)

**Shared Program:** https://makecode.com/_0ji3UvTDg4Ds

## Challenges

Try the following challenges to get more practice with events.

### Challenge 1 - Make Ocelots Appear

Change the existing code so five ocelots appear when you break grass blocks.

### ~ hint

The [ocelot](https://en.wikipedia.org/wiki/Ocelot) is a wild cat native to the Southwestern United States, Mexico, and Central and South America.

### ~

### Challenge 2 - Print "Broken" in TNT

Let's change what happens when grass is broken. Now let's print the word "broken" in TNT.

### ~ hint

Use search to find `print`, and use these coordinates so the printing starts a bit away from you!

![print broken coordinates](/static/courses/csintro/events/print-broken-coordinates.png)

### ~

## Experiments

Here there are no rules... Copy the code and change things around to see what kind of results you can create. Suggestions are given, but do as you like!

### Experiment 1 - AutoCake

Move a cake into your inventory automatically. You can run this in the game without manually adding a cake to your player inventory. What other things could you give yourself at start????

### Experiment 2 - Chained Events

Here you can see a chained event. You break cake to spawn parrots, and if you kill parrots you spawn skeleton horses. Can you make other cause-and-effect chains?