# Why Learn Coordinates?

In Minecraft, it’s important to know where you are in the world, where your agent is, and where all kinds of things from diamond mines, to woodland mansions, to underground spawners are. In Survival mode, it’s even more important to be able to get back to a safe place when the sun starts to go down, or to remember the location of points of interest so you can find them again if your inventory is full and you need to come back.

Even if you are already familiar with moving around in Minecraft, you might not have used coordinates, except perhaps to teleport. In order to use many of the MakeCode blocks effectively, you need to understand Minecraft *coordinates*, which are also known as *positions*.

## Coordinates in Minecraft

Minecraft uses a set of three coordinates (X, Y, and Z) to specify a position in a Minecraft world. MakeCode for Minecraft uses these coordinates in many of its blocks to specify where an action should take place.

Search the web for more information about the 3-dimensional axes.

Just as in a three-dimensional coordinate grid in math class, there is an origin point (0, 0, 0) where all three axes meet, and the coordinates X, Y, and Z represent distances from this point.

**(X):** The X coordinate represents a distance along the horizontal plane east or west of the origin, just like in real-world longitude values.

* A distance east of the origin is represented by a positive X value, (+X).
* A distance west of the origin is represented by a negative X value, (-X).

In the picture shown earlier, you might also think of this as length.

**(Y):** The Y coordinate represents a distance along the vertical plane up or down from the origin, just like in real-world altitude values.

* A distance up from the origin is represented by a positive Y value, (+Y).
* A distance down from the origin is represented by a negative Y value, (-Y).

Again, in the picture, you might also call this height.

**(Z):** The Z coordinate represents a distance north or south of the origin, just like in real-world latitude values.

* A distance south of the origin is represented by a positive Z value, (+Z).
* A distance north of the origin is represented by a negative Z value, (-Z).

In the picture, this could be considered width.

![Minecraft position](/static/courses/csintro/coordinates/minecraft-position.jpg)

In the example just shown, your world position in this Minecraft world is currently (3, 98, 0). These numbers represent how far away you are from the world origin point (0, 0, 0).

* X = 3 means that you are three blocks east of the origin point.
* Y = 98 means that you are 98 blocks above the origin point.
* Z = 0 means that you are at the north-south origin.

To see where you are in Minecraft, press the function key `F1`. Your world position (X, Y, Z) coordinates will appear in the upper-left corner of your Minecraft window.

Try walking around in Minecraft and see how these values change. Press the spacebar to jump, and notice that your altitude (the Y value) changes, momentarily, by +1. If you are flying, Y will change a lot.

## Absolute world position versus relative player position

There are two different kinds of positions in Minecraft:

**Absolute world position** = A position that is based on position in the world (in other words, the distance from the world's (0, 0, 0) to an object or entity)   


* Could be far down in the ground  
    
* Is visible in the game if you press `F1`  
    

![Absolute World Position](/static/courses/csintro/coordinates/absolute-world-position.png)

**Relative player position** = A position that is based on where the player is (in other words, the distance from the player to an object or entity)  


* Distance FROM PLAYER TO object or entity   
    
* Not visible in game   
    

![Relative Player Position](/static/courses/csintro/coordinates/relative-player-position.jpg)

Here the block is five blocks west and five blocks north of the character. Both the player and the block are at the same height (65) or level of the Y axis.

### Absolute world position

**Based on the world (from the world's (0, 0, 0) to an object or entity)**

An absolute world position is made up of three numbers that represent the distance from the Minecraft world origin of (0, 0, 0). Just as in real life, the world positions are fixed and do NOT change, no matter where the player currently is in the Minecraft world.

For example, in real life:

* The earth’s geographical origin point, where latitude and longitude are both zero, is marked by a weather buoy off the coast of Africa, placed where the earth's equator meets the Greenwich Prime Meridian.

Search the web for more information about a Weather buoy moored at coordinates 0°N 0°E (fictitious Null Island)

* Mount Everest has world coordinates of 27° north and 86° east of the origin point.

Search the web for more information about Mount Everest at 27°N 86°E.

* The Empire State Building has world coordinates of 40° north and 73° west of the origin point.

Search the web for more information about The Empire State Building at coordinates 40°N -73°E.

### Relative player position

**Based on where the player is (from the player to an object or entity)**

The relative position is the distance from your player to whatever it is you are talking about. Relative positions are denoted by a **~** (tilde) symbol before each of the three numbers that make up the three-coordinate (~X, ~Y, ~Z) position.

Minecraft players are two blocks tall, so (~0, ~0, ~0) represents the player’s feet and (~0 ~1 ~0) represents the player’s head. As a player moves around in Minecraft, so do the player’s feet, which means the relative position is NOT a fixed position – it changes as the player moves around in the game.

For example, wherever the player is in the Minecraft world:

* (~0, ~2, ~0) will always represent the location just above the player’s head.
* (~5, ~0, ~0) will always represent the location five blocks east of the player’s current position.
* (~0, ~3, ~-3) will always represent the block two blocks above the player’s head and three blocks north of the player’s current position.

![relative positions in Minecraft](/static/courses/csintro/coordinates/minecraft-relative.jpg)