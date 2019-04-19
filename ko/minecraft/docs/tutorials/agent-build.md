# 에이전트로 건축하기

## Introduction @unplugged

에이전트가 무언가를 건축하게 할 수 있습니다. 이 튜토리얼에서는`||agent:agent place on move||`블록을 활용하는 방법을 배울 것 입니다. 이 블록은 에이전트가 이동할때마다 블록을 놓게 할 수 있습니다. 이를 위해 에이전트에게 블록을 놓고 앞으로 가도록 채팅명령어를 입력할 것입니다. 에이전트가 회전(방향 전환)을 하게 하기 위해서 명령을 추가할 수도 있습니다. 에이전트에게 이러한 명령을 내려서 원하는 모양을 만들게 할 수 있습니다. 이 튜토리얼에서는 사각형을 만들 것입니다.

![에이전트가 당신을 위하여 건설합니다.](/static/tutorials/agent-build.gif)

## 단계 1

Go to your Agent in Minecraft and equip him with blocks. Can't find your Agent? Add a chat command with the `||agent:agent teleport to player||` block.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## 단계 2

Add a new chat command **pd** (for "**p**en **d**own") and place a `||agent:agent place on move||` block to tell the Agent to place a block as it moves.

```blocks
player.onChat("pd", function () {
    agent.setAssist(AgentAssist.PlaceOnMove, true)
})
```

## 단계 3

Add a chat command **fd** (for "**f**orwar**d**") that **moves** the Agent by `3` blocks.

```blocks
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 3);
})
```

## 단계 4

Go to Minecraft, press **t** to open the chat. Enter **pd** then enter **fd** to get the Agent to build a wall.

Make sure to press **Enter** in the chat after each command.

## 단계 5

Add a chat command to build a **square** by combining `||agent:agent move||` and `||agent:agent turn||` blocks.

You can create a sequence of commands that the Agent will execute in order. Try to decompose the different steps, **move** or **turn** needed to build a square.

```blocks
player.onChat("square", function () {
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
    agent.move(SixDirection.Forward, 3);
    agent.turn(TurnDirection.Left);
});
```

## 단계 6

That was an awful lot of blocks! Use the `||loops:for||` block to repeat code.

The `||loops:for||` block tells the computer to repeat the code under it.

```blocks
player.onChat("square", function () {
    for (let i = 0; i <= 3; i++) {
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
    }
});
```

## 단계 7

Ouch the Agent keeps hitting the last block! Use the `||agent:agent detect||` and `||logic:if||` blocks to move up if a block is in the way.

The `||logic:if||` block runs the code under `||logic:then||` if that `||agent:agent detect||` returns **true**.

```blocks
player.onChat("square", function () {
    for (let i = 0; i <= 3; i++) {
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
        if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
            agent.move(SixDirection.Up, 1)
        }
    }
});
```