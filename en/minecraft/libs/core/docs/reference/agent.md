# Agent

The **agent** is your assistant who helps you do things in Minecraft. You command the agent with the `||agent:agent||` blocks.

Your agent appears when you teleport it to you. When you have your agent, it can do work for you. Give things from your inventory to your agent and have it build stuff for you. Use the `||agent:agent place||` action to make the agent place a block somewhere.

You make your agent go in different directions by moving, turning, and detecting blocks in the way.

## Reference

```cards
agent.teleportToPlayer();
agent.move(SixDirection.Forward, 1);
agent.turn(TurnDirection.Left);
agent.detect(AgentDetection.Block, SixDirection.Forward);
agent.setAssist(AgentAssist.PlaceOnMove, false);
```

## Actions

```cards
agent.place(SixDirection.Back);
agent.destroy(SixDirection.Forward);
agent.till(SixDirection.Forward);
agent.attack(SixDirection.Forward);
agent.setSlot(1);
agent.collectAll();
agent.collect(blocks.item(Item.IronShovel));
agent.inspect(AgentInspection.Block, SixDirection.Forward);
```

## Inventory

```cards
agent.transfer(
    1,
    1,
    2
);
agent.drop(
    SixDirection.Back,
    1,
    1
);
agent.dropAll(SixDirection.Forward);
agent.getItemCount(1);
agent.getItemSpace(1);
agent.getItemDetail(1);
```