# teleport To Player

Teleport the agent to the player.

```sig
agent.teleportToPlayer();
```

## Example

Bring the agent to the player when "come" is typed in the game chat.

```blocks
player.onChat("come", function () {
    agent.teleportToPlayer();
});
```