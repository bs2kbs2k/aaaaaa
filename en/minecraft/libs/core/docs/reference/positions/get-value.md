# get Value

Get the value of the distance in one direction of a position. This is the coordinate value of **x**, **y** or **z**.

```sig
positions.create(0, 0, 0).getValue(Axis.X);
```

## Parameters

* **direction**: the direction (axis) of the coordinate value you want: > `x (East/West)`, `y (up/down)`, or `z (North/South)`

## Example

Display the player's current altitude in the game chat. The altitude is the `y` coordinate of the player's current world position.

```blocks
player.say("My current altitude is: " + player.position().getValue(Axis.Y));
```