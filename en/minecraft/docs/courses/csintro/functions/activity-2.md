# Activity: Zombie Pig

Create another mini-game that instantly transforms pigs into an army of Zombie Pigmen to combat! If you spawn Zombie Pigs and cannot defeat them, you lose. Luckily, you’ll build this mini-game in MakeCode by using functions, so you can try again and again.

Our mini-game will have three parts:

1. Creating the Zombie Pigs
2. Creating strange time lapses
3. Setting the gamemode & difficulty

## Do the activity

### Make a function

1. Create a new MakeCode project called **Zombie Pig**.

2. Click the Advanced tab on the Toolbox to display more Toolbox categories.

3. In `||functions:FUNCTIONS||`, click the **Make a Function** button.

![Make a Function](/static/courses/csintro/functions/make-a-function.png)

### Name the function

1. Name this function `zombiepig`, and click **Ok**.

### Make the *atmosphere()* and *setup()* functions

1. Repeat the previous step to create two more functions named: `atmosphere` and `setup`.

2. From `||player:PLAYER||`, drag a `||player:on chat command||` block onto the Workspace.

3. Rename this `||player:on chat command||` to `"play"`.

4. From `||functions:FUNCTIONS||`, drag the three blocks `||functions:call function setup||`, `||functions:call function atmosphere||`, and `||functions:call function zombiepig||` into the `||player:on chat command "play"||`.

```blocks
function zombiepig()  {

}
function atmosphere()  {

}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
function setup()  {

}
```

`||player:on chat command "play"||` will be the main code that starts your mini-game. Now, let’s build out the three functions that will accomplish your goals.

Your mini-game will have three parts:

1. Creating the Zombie Pigs
2. Creating strange time lapses
3. Setting the game mode & difficulty

### Create the Zombie Pig

The first thing you’ll do is create a Zombie Pig.

1. From `||mobs:MOBS||`, drag a `||mobs:spawn animal||` block into `||functions:zombie pig||`. Change the animal by selecting `Pig` from the drop-down menu. Then change the position in the Z coordinate to spawn a pig five blocks north of the player.

2. Repeat step 9 to create another spawn block and place it below the first.

3. Replace **animal** with a projectile lightning bolt.

4. Enter the same coordinates used for the pig: `(~0, ~0, ~-5)`.

The trick here is that if a pig is hit by lightning, it transforms the pig into a Zombie Pigman! This is why you want to spawn both at the same coordinates `(~0, ~0, ~-5)`.

```blocks
function zombiepig() {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0, 0, -5))
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
function setup()  {

}
function atmosphere()  {

}
```

### Adjust settings

You want the game to work automatically. After you enter **play**, the game should start with everything set up so you have some crazed Zombie Pigmen to battle.

The first issue is the difficulty level of the game. The pig will not change into a Zombie Pig if the game is set to Peaceful.

1. From `||gameplay:GAMEPLAY||`, drag a `||gameplay:set difficulty to||` into `||functions:setup||`.

2. Adjust this new block so it reads `||gameplay:set difficulty to 'peaceful'||`.

Next, you want to change the game mode for your player. Setting the gamemode to Survival mode ensures that the Pigman will come after you! As soon as you hit the Pigman, it will start to attack you back!

1. From `||gameplay:GAMEPLAY||`, drag a `||gameplay:change game mode to||` into `||functions:setup||`.

2. Adjust this new block so it reads `||gameplay:change game mode to 'survival'||`.

3. Also, adjust the target so that it targets "yourself".

Finally, fighting will be very difficult without a weapon. You can give yourself a weapon to make the game more reasonable for your player.

1. From `||mobs:MOBS||`, grab a `||mobs:give||` block and place it as the last block in the `||functions:setup||` function.

2. You will need to target yourself and give yourself a sword or other weapon. The example gives one diamond sword.

```blocks
function atmosphere()  {

}
function setup() {
    gameplay.setDifficulty(GameDifficulty.Easy)
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.DiamondSword),
    1
    )
}
function zombiepig() {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0, 0, -5))
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```

At this point, you can test your game!

By entering **play** in the chat window, the mini-game will start.

![Mini-Game with ZombiePig & Settings](/static/courses/csintro/functions/minigamewithouttime.jpg)

### Adjust time

The last step for this mini-game is to add visual effects by adjusting the time of day. This will give the appropriate atmosphere that all zombies require. You will add a **time set** block. You can find this by using the **Search** bar or looking in `||gameplay:GAMEPLAY||`.

A Minecraft day lasts 24,000 ticks for 20 minutes of play.

By setting the game to midnight, you set the current time to the start of midnight. Time set blocks are an easy way to make time move to a common part of the day. Midnight is equal to 18,000 ticks (12:00 AM).

1. From `||gameplay:GAMEPLAY||`, drag a `||gameplay:time set||` block into the `||functions:atmosphere||` function.

2. Adjust this to read `||gameplay:time set 'midnight'||`.

```blocks
function atmosphere() {
    gameplay.timeSet(gameplay.time(DayTime.Midnight))
}
function setup() {
    gameplay.setDifficulty(GameDifficulty.Easy)
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.DiamondSword),
    1
    )
}
function zombiepig() {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0, 0, -5))
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```

1. Go to Minecraft, enter **t** to open the chat, enter **play**, and then press Enter.

## ~ hint

**Time not changing?**

Make sure the **Always Day** option isn’t turned on.

## ~

### Spawn additional Pigmen

After defeating a pigman, you want another pigman to spawn. You can create a new pigman with the event `||on Mob killed||`. You will use the function `||call Pigman||`.

1. From `||mobs:MOBS||`, grab a `||mobs:on animal killed||` event and place it on the Workspace.

2. Adjust this block so that it is `||mobs:on monster zombie pigman killed||`.

3. Add a `||functions:call function zombiepig||` to this new event.

```blocks
function setup() {
    gameplay.setDifficulty(GameDifficulty.Easy)
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.DiamondSword),
    1
    )
}
mobs.onMobKilled(mobs.monster(MonsterMob.PigZombie), function () {
    zombiepig()
})
function atmosphere() {
    gameplay.timeSet(gameplay.time(DayTime.Midnight))
}
function zombiepig() {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0, 0, -5))
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})

```

For more of a challenge, spawn more Zombie Pigmen in the event you just added. You could use a loop to call the function multiple times.

## Give the full game a try!

![Mini-Game get sword](/static/courses/csintro/functions/playswordgamemodechange.jpg)

![Mini-Game move position](/static/courses/csintro/functions/playswordgamemodechange1.jpg)

![Mini-Game survival mode](/static/courses/csintro/functions/playswordgamemodechangeattack.jpg)

![Mini-Game attack pigman](/static/courses/csintro/functions/attackpigman.jpg)

![Mini-Game do battle](/static/courses/csintro/functions/playerpigmanbattle.jpg)

## Challenges

Let's change some things to make our own different and unique situations!

### Challenge 1 - Function to Keep Score

Put the following blocks in the code from the activity. If you put these blocks in the correct places, your scoreboard should work!

```blocks
let scoreNum = 0
scoreNum = 0

scoreNum += 1

function score() {

}

score()

player.say("Currently you have " + ("" + scoreNum + " points."))
```

### Challenge 2 - Function to Randomize Position

Create a function that chooses a random position so the pigmen are not as predictable.

You will need to:

1. Create random numbers for X and Y coordinates and then store everything into one variable. Going farther than 10 blocks away from your character might make the game unplayable, so you could use the default setting (0-10) for random number generation.

2. Call this new function in the right place so pigmen are spawned in random places.

## Experiments

Try out this code and just have fun! Add things if you can or just take note of what you see. You might remember something later, and you can use some of this code for a future project.

### Experiment 1 - Lots of Pigmen and Lots of Lightning

The on chat command is actually a function. It is the most powerful function because you can pass in variables. Passing in information to a function is super powerful. Here, you are able to do a lot with just this one on chat command because it calls itself.

Can you figure out what it is doing?

### Experiment 2 - Flashlight

Combining events and functions can get some cool results. It is difficult to see at night, and you may want to know what you are standing on. This code calls a function to test what you are standing on as you walk and returns a message if you are standing on grass.

What else could you detect for?

This is similar to the work you will do for the artificial intelligence lesson.