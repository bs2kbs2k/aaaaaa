# 위치

A **position** represents a location in the Minecraft world. Positions are used in many blocks and commands to spawn mobs, fill blocks and more...

A position is represented by 3 numbers, **x**, **y**, and **z**:

* **x**: East (positive, +x) or West (negative, -x), also known as **longitude** in the real world
* **y**: up (positive, +y) or down (negative, -y), altitude or **elevation**
* **z**: South (positive, +z) or North (negative, -z), also known as **latitude** in the real world

The numbers for **x**, **y**, and **z** are the *coordinates* (a coordinate is also known as a direction or an axis) of the position.

### ~ hint

![](/static/mods/3d-axis.jpg)

Need to visualize x, y, z? **[Try the 3D Axis example](/examples/3d-axis)** to see the x, y, z axes.

Need to know where East, West, South, North are pointing to? **[Try the compass](/examples/compass)** to visualize cardinal directions.

### ~

There are two kinds of positions: a **relative** position and a **world** position.

### Relative positions

A **relative position** has **~** before each number and is centered on the player's current position: **(~0, ~0, ~0)**. Players are two-block tall, so it is important to note that the position **(~0, ~0, ~0)** corresponds to the player's **feet**.

Because relative positions start from where the player's feet are, relative positions aren't fixed in the world - they "move" with the player. For example, the relative position **(~0, ~2, ~0)** will always correspond to the block that is currently above the player's head, no matter where the player is in the world. If the player moves, then **(~0, ~2, ~0)** is no longer at the same block as before the player moved. Keep this in mind when using relative positions in your code!

You can create a relative position using the `||positions:~0 ~0 ~0||` block.

Here are more examples of relative positions:

* The position of the player's head is **1 block above** their feet, its relative position is **(~0, ~1, ~0)**.
* The position of the block **1 block East** of the player is **(~1, ~0, ~0)**.
* The position of the block **2 block West, 5 blocks down** of the player is **(~-2, ~-5, ~0)**.

### World positions

A **world position** is 3 numbers that are the distances in each direction from the world origin: **(0, 0, 0)**. This is also called an *absolute* position. World positions aren't changed by the player's current position. They always stay the same. For example, the position **(5, 2, 15)** will always mean the same block in the world, no matter where the player is.

You can create a world position using the `||positions:world 0 0 0||` block.

### ~ hint

Enter **/position** in Minecraft to see your current **world** position in the top left corner of Minecraft. You can also use the `||player:player world position||` block in your code. This way, no matter where you are in the game world, your code can use your position to do things near you.

### ~

### Math operators

You can add two positions to create a new one.

```blocks
let p = positions.add(player.position(), positions.create(10, 15, 20));
```

## 찾아보기

```cards
positions.create(0, 0, 0);
positions.createWorld(0, 0, 0);
positions.add(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
positions.random(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
positions.create(0, 0, 0).getValue(Axis.X);
positions.create(0, 0, 0).toWorld();
positions.create(0, 0, 0).toString();
```