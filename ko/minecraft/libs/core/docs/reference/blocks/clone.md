# clone

Clone, make a copy of a cubic region from one location into a another location.

```sig
blocks.clone(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
);
```

## 매개 변수

* **begin**: the first corner of the cubic region
* **end**: the opposite corner of the cubic region
* **destination**: the first corner of the destination region
* **mask**: how to handle air blocks: > * `replace`: clone everything into the new region, including air blocks > * `masked`: air blocks from the cloned region are ignored; their corresponding blocks in the destination region are not changed
* **mode**: how to handle the cloned region: > * `normal`: the cloned region is not changed; if the destination region overlaps it, then the clone operation does nothing > * `force`: the cloned region is overwritten by the destination region if the two regions overlap > * `move`: the cloned region is replaced with air after the cloning

The clone command in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#clone) describes how cloning works.

## 예시

Create a ceiling above the current player's head. This copies the floor below the player's feet to the ceiling.

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    blocks.clone(
        positions.create(-2, -1, -2),
        positions.create(2, -1, 2),
        positions.create(-2, 3, 0),
        CloneMask.Replace,
        CloneMode.Normal
    );
});
```

## 참고 항목

[`||blocks:clone filtered||`](/reference/blocks/clone-filtered)