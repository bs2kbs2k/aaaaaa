# Activity: Tile Map

Maps and levels form the basis of many of the most common types of video games; they allow a canvas for the games story to progress, and for the player to explore.

In @boardname@, `||scene:tile maps||` provide an easy way to design two dimensional maps.

In this activity, students will:

* Edit a tile map
* Personalize the tiles in the tile map
* "Decorate" a house

## Concept: Editing a tile map

The tile map uses an image to represent a game space that is often much larger than the visible game screen.

Each pixel in a tile map image translates to and area of 16x16 pixels on the 160x120 pixel game screen.

A `|scene:tile map|` is called a "Map" because it "maps" a tile map color to image that is stored as a tile.

### Example #1: Making a tile map

https://youtu.be/eBLl_sQ2bGU

[Alternative Video Location](https://aka.ms/40544a-intro-tilemap)

1. Review the code below
2. Copy the code below into your project and run it

```blocks
scene.setTileMap(img`
1 1 1 1 1 1 1 1 1 1 
1 1 1 5 1 1 5 1 1 1 
1 1 1 5 1 1 5 1 1 1 
1 1 1 1 1 1 1 1 1 1 
1 1 5 1 1 1 1 5 1 1 
1 1 1 5 5 5 5 1 1 1 
1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 
`)
```

In this example, we have used `||scene:set tile map to||` to set the tile map to an image of a smile; the smile shows up on the screen, effectively replacing the standard black background.

## Student Task #1: Personalized tile map

1. Start with example #1
2. Modify the image to create a tile map of your creation (name it "intro tile map 1")

### Example #2: Creating tiles in a tile map

https://youtu.be/S2fHt1qqCYY

[Alternative Video Location](https://aka.ms/40544a-tile-in-tilemap)

1. Review the code below
2. Copy the code below into your project and run it

```blocks
scene.setTileMap(img`
1 1 1 1 1 1 1 1 1 1 
1 1 1 5 1 1 5 1 1 1 
1 1 1 5 1 1 5 1 1 1 
1 1 1 1 1 1 1 1 1 1 
1 1 5 1 1 1 1 5 1 1 
1 1 1 5 5 5 5 1 1 1 
1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 
`)
scene.setTile(5, img`
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 a 
5 5 5 6 6 6 6 6 6 6 6 6 6 5 a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 6 6 6 6 6 6 6 6 6 6 a a a 
5 5 5 a a a a a a a a a a a a a 
5 5 a a a a a a a a a a a a a a 
5 a a a a a a a a a a a a a a a 
`)
```

## Student Task #2: Add tile to tile map

1. Start with your "intro tile map 1" code and name "tile in tile map"
2. **Modify** the code to include a tile image that is used in the tile map

### Example #3: Words!

https://youtu.be/bqU8zBSoKl4

[Alternative Video Location](https://aka.ms/40544a-tile-words)

1. Make a new project (name it "tilemapWords")
2. Review the code below
3. Copy the code below into your project and run it

```blocks
scene.setTileMap(img`
. . . . . . . . . . 
. . . . . . . . . . 
. . . . . . . . . . 
. . 6 5 7 8 . . . . 
. . . . . . . . . . 
. . . . . . . . . . 
. . . . . . . . . . 
. . . . . . . . . . 
`)
scene.setTile(2, img`
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 1 1 1 1 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
`)
scene.setTile(3, img`
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f 1 1 1 1 1 1 1 f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 1 1 1 f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 1 1 1 1 1 1 f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
`)
scene.setTile(6, img`
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f 1 f f f f f f 1 f f f f 
f f f f 1 f f f f f f 1 f f f f 
f f f f 1 f f f f f f 1 f f f f 
f f f f 1 f f f f f f 1 f f f f 
f f f f 1 f f f f f f 1 f f f f 
f f f f 1 f f f f f f 1 f f f f 
f f f f 1 f f 1 1 f f 1 f f f f 
f f f f 1 f 1 f f 1 f 1 f f f f 
f f f f 1 1 f f f f 1 1 f f f f 
f f f f 1 f f f f f f 1 f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
`)
scene.setTile(5, img`
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f 1 1 1 1 1 1 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 f f f f f 1 f f f f f 
f f f f 1 1 1 1 1 1 1 f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
`)
scene.setTile(4, img`
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 f f f f f f f f f f f 
f f f f 1 1 1 1 1 1 1 f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
`)
scene.setTile(7, img`
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f 1 1 1 1 f f f f f f f 
f f f f f 1 f f f 1 f f f f f f 
f f f f f 1 f f f 1 f f f f f f 
f f f f f 1 f f f 1 f f f f f f 
f f f f f 1 f f f 1 f f f f f f 
f f f f f 1 1 1 1 1 f f f f f f 
f f f f f 1 f f 1 f f f f f f f 
f f f f f 1 f f f 1 f f f f f f 
f f f f f 1 f f f 1 f f f f f f 
f f f f f 1 f f f 1 f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
`)
scene.setTile(8, img`
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f 1 1 1 1 1 f f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 f f f f 1 f f f f f f 
f f f f 1 1 1 1 1 f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
`)
```

In this example, there is a new block being used: `||scene:set tile to||`

The `||scene:set tile to||` blocks allow us to personalize how the tile shows up on the screen. Here, we have created a few images containing letters of the alphabet, assigned to different color tiles, with `||scene:set tile map to||` set to create a tile map with the tiles necessary to display "word" on the background.

## Student Task #3: Hello World!

1. Start with the code from example #3
2. Change the `||scene:tile map||` image so that it displays "Hello World" instead of just "Word"
3. **Challenge:** Create a new tile with an exclamation mark, and change the tile map so that "Hello World**!**" is displayed

### Example #4: A brand new home

https://youtu.be/YHYBQ03ecOk

[Alternative Video Location](https://aka.ms/40544a-tilemap-home)

1. Make a new project (name it "newHome")
2. Review the code below
3. Copy the code below into your project and run it

[NewHome project](https://makecode.com/_2X5PdkLjp5p5)

```blocks
enum SpriteKind {
    Player,
    Enemy
}
let HomeOwner: Sprite = null
HomeOwner = sprites.create(img`
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . f f f f f f . . . . . 
. . . . . f f f f f f . . . . . 
. . . . . f 9 f 9 f f . . . . . 
. . . . . f f f f f f . . . . . 
. . . . . f f f f f f . . . . . 
. . . . . . . . f . . . . . . . 
. . . . . . . f f f . . . . . . 
. . . . . . . . f . . . . . . . 
. . . . . . . . f . . . . . . . 
. . . . . . . f . f . . . . . . 
. . . . . . . f . f . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
`, SpriteKind.Player)
scene.setTileMap(img`
f f f f f f f f f f f f f f f f f f f f f f f f f f f f f f f f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f f f f 1 1 f f f f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 f 
f f f f f f f f 1 1 f f f f f f 1 1 f f f f f f f f 1 1 f f f f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f f f f f f f f f 1 1 f f f f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f f f f f f f f 1 1 f f f f f f f f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 f 1 1 1 1 1 1 1 1 1 1 1 1 1 f 
f f f f f f f f f f f f f f f f f f f f f f f f f f f f f f f f 
`)
scene.setTile(15, img`
f f f f f f f f f f f f f f f f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f f f f f f f f f f f f f f f f 
f f f f f f f f f f f f f f f f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f d d d d d d f f d d d d d d f 
f f f f f f f f f f f f f f f f 
`, true)
scene.setTile(2, img`
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 e e e e e e e e e 1 1 
1 1 1 1 1 e e e e e e e e e 1 1 
1 1 1 1 1 d d d d d e e e e 1 1 
1 1 1 1 1 d 1 1 1 d d 1 e e 1 1 
1 1 1 1 1 d d d d d d 1 e e 1 1 
1 1 1 1 1 d 1 d 1 d d 1 e e 1 1 
1 1 1 1 1 d d 1 d 1 d 1 e e 1 1 
1 1 1 1 1 d d d d d d 1 e e 1 1 
1 1 1 1 1 d 1 1 1 d d 1 e e 1 1 
1 1 1 1 1 d d d d d e e e e 1 1 
1 1 1 1 1 e e e e e e e e e 1 1 
1 1 1 1 1 e e e e e e e e e 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
`, true)
scene.setTile(3, img`
1 1 9 9 9 9 9 9 9 9 9 9 9 9 9 1 
1 1 9 9 9 1 1 1 1 1 1 1 9 9 9 1 
1 1 9 9 9 1 d 1 d 1 d 1 9 9 9 1 
1 1 9 9 9 1 d 1 d 1 d 1 9 9 9 1 
1 1 9 9 9 1 1 1 1 1 1 1 9 9 9 1 
1 1 9 9 9 9 9 9 9 9 9 9 9 9 9 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
1 1 6 6 6 6 6 6 6 6 6 6 6 6 6 1 
`, true)
scene.setTile(4, img`
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 e e e e e e e e e e 1 1 1 
1 1 e e e d e 7 1 1 e e e e 1 1 
1 e e e a d e 1 1 1 e e e e e 1 
1 e e e e e e e e e e e a e e 1 
1 e e e e e e f f e e e d d e 1 
1 e 7 1 e e f f f f e e 1 1 e 1 
1 e 1 1 e e f 1 1 f e e 1 1 e 1 
1 e 1 1 e e f f f f e e 1 7 e 1 
1 e d d e e e f f e e e e e e 1 
1 e e a e e e e e e e e e e e 1 
1 e e e e e e e e e e e e e e 1 
1 e e e e e 1 1 1 e d a e e e 1 
1 1 e e e e 1 1 7 e d e e e 1 1 
1 1 1 e e e e e e e e e e 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
`, true)
scene.setTile(5, img`
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 a a a 1 1 1 1 1 1 1 1 
1 1 1 1 a a c a a 1 1 1 1 1 1 1 
1 1 1 a a c a a a a 1 1 1 1 1 1 
1 1 a a c a a a a a a 1 1 1 1 1 
1 1 a a a a c a a c a 1 1 1 1 1 
1 1 a a a c a a c a a 1 1 1 1 1 
1 1 1 a c a a c a a 1 1 1 1 1 1 
1 1 1 1 a a a a a 1 1 1 1 1 1 1 
1 1 1 1 1 a a a 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
`, false)
game.onUpdate(function () {
    controller.controlSprite(HomeOwner, 100, 100)
})
```

For the "newHome" example, we have made a tile map that is significantly larger than the screen size by increasing the size to 32x32 within the `||scene:tile map||` image editor.

![image: tile map editor](/static/courses/csintro1/tilemap/tilemap-editor.png)

We've created a few tiles with `||scene:wall||` set to on - this means that the player won't be able to move through them.

The example tiles that are provided here are the following:

* The black tile represents a wall
* The red tile represents a chair
* The pink tile represents a bed
* The orange tile represents a table
* The purple tile represents a rug

## Student Task #4: Decorate and move around the house

1. Start with the code from example #4
2. Make the camera follow the sprite by adding the `||scene:camera follow sprite||` block to the `||loops:on start||` block and set it to follow the `||variables:homeOwner||`
3. Add home furnishings around the house, by changing some of the white tiles to be some of the other provided tiles
4. Create another tile with a different image, and place that tile around the house to personalize it
5. **Challenge:** create two more tiles with different sprites, and place them around the house as well. 

## What did we learn?

1. What is the default size when you create a new tile map? Does it perfectly match the screen size?

### ~hint

Open the tile map from the first example in the image editor; it will give the dimensions of the tile map in the bottom-left corner. When displayed on the screen, each tile in that tile map will be a 16x16 square.

As a reminder, the `||scene:screen height||` is 120 pixels, and the `||scene:screen width||` is 160 pixels.

### ~

2. When `||scene:camera follow sprite||` is set to follow a sprite, does that sprite always stay in the center of the screen, or are there times where it somewhere else on the screen? Explain how you know.