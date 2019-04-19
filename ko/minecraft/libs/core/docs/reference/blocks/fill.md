# fill

Fill a volume of blocks in between two positions.

```sig
blocks.fill(
        blocks.block(Block.Grass),
        positions.create(0, 0, 0),
        positions.create(0, 0, 0),
        FillOperation.Replace
    );
```

## 매개 변수

* **block**: the block used to fill the volume
* **from**: the first corner of the cubic region
* **to**: the opposite corner of the cubic region
* **operator**: what happens to the existing blocks in the region. Choose one of these options: > * `replace`: all blocks inside the fill region are replaced with the specified block, including air > * `hollow`: only blocks on the outer edge of the fill region are replaced with the specified block; blocks inside the region are replaced with air > * `outline`: only blocks on the outer edge of the fill region are replaced with the specified block; blocks inside the region are not be changed > * `keep`: only air blocks inside the fill region are replaced with the specified block; existing blocks are not be changed > * `destroy`: same as `replace`, but existing blocks are dropped as items as if they had been mined by the player

The way **fill** works is described in this [Minecraft wiki](http://minecraft.gamepedia.com/Commands#fill) section.

## 예시

Create **a lot of TNT blocks!**!

```blocks
blocks.fill(
    blocks.block(Block.TNT), 
    positions.create(1, 1, 1), 
    positions.create(10, 10, 10),
    FillOperation.Replace
    );
```

If you want to see it in action, the **fill** block is used in the [1000 TNT](/examples/1000-TNT) example.