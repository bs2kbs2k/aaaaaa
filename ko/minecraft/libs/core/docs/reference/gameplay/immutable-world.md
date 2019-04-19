# immutable World

Control the ability for players to alter the world.

```sig
gameplay.immutableWorld(false);
```

## 매개 변수

* **enabled**: `true` if modifying the world is allowed, `false` if not allowed

## 예시

Make the world immutable when someone tries to destroy stone blocks.

```blocks
blocks.onBlockBroken(blocks.block(Block.Stone), () => {
    player.say("No griefing!");
    gameplay.immutableWorld(true);
});
```