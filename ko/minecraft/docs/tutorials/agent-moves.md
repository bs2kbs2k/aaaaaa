# 에이전트 이동

## Introduction @unplugged

에이전트를 움직여 봅시다. 이 튜토리얼에서는 채팅명령을 통해 에이전트가 움직이고 회전하는 방법을 배웁니다.

![Make your agent dance!](/static/tutorials/agent-moves.gif)

## 단계 1

`||player:on chat command||` 명령블록을 놓고, **"tp"**라고 입력하세요.

```blocks
player.onChat("tp", function () {

})
```

## 단계 2

`||agent:agent teleport to player||` 명령블록을 `||player:on chat command||` 명령블록 안으로 넣어주세요.

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## 단계 3

마인크래프트로 가서, 채팅창을 열기 위해 **t**키를 눌러 **tp**를 입력하세요.

## 단계 4

Place a `||player:on chat command||` block and rename it **"fd"**. Place a `||agent:agent move||` block to **move** the Agent **forward** by 5 blocks.

```blocks
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 5)
})
```

## 단계 5

Go to Minecraft and enter **fd** in the chat. Will the Agent move?

## 단계 6

Place a new **lt** chat command to turn the Agent **left** using the `||agent:agent turn||` block.

```blocks
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
```

## 단계 7

Place a new **rt** chat command to turn the Agent **right**.

```blocks
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
```

## Step 8

Go to Minecraft and enter commands `tp`, `rt`, `lt` or `fd` in the chat to control your Agent!