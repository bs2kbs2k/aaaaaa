# Flower Trail

## Introduction @unplugged

Leave a **trail of dandelions** everywhere you go.

![A flower trail](/static/tutorials/flower-trail.gif)

## 단계 1

Rename **"run"** to **"trail"** in the `||player:on chat command||` block.

```blocks
player.onChat("trail", function () {
})
```

## 단계 2

Put a `||blocks:place||` block inside the chat command, and click the image to select a **flower**. The numbers (**~0 ~0 ~0**) mean the flower will be placed at your current position.

```blocks
player.onChat("trail", function () {
    blocks.place(blocks.block(Block.YellowFlower), positions.create(0,0,0))
})
```

## 단계 3

Go to Minecraft, press **t** to open the chat and enter **trail** to run your code.

## 단계 4

Place a `||loops:repeat||` block and move the `||blocks:place||` inside of it to create **100** flowers.

```blocks
player.onChat("trail", function () {
    for(let i = 0; i < 100; i++) {
        blocks.place(blocks.block(Block.YellowFlower), positions.create(0,0,0));
    }
})
```

## 단계 5

Go to Minecraft and enter **trail** in the chat to run your code.

## 단계 6

Not really into flowers? Try selecting **sand** in the `||blocks:place||` block, it also falls when placed in the air.

```blocks
player.onChat("trail", function () {
    for(let i = 0; i < 100; i++) {
        blocks.place(blocks.block(Block.Sand), positions.create(0,0,0))
    }
})
```

## 단계 7

Go to Minecraft and enter **trail** in the chat to run your code. Watch for sand!