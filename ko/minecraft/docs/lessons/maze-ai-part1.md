# Artificial intelligence - Part 1

Students collaboratively build mazes and write AI to solve their own mazes.

## Learning objectives

Understand the importance of dividing up work, collaborating with others, designing before building, and adjusting designs based on new input.

## ~ hint

#### Applicability

**Skill areas**: Speaking and Listening, Collaboration, Roles

**Ages**: 11-13 yrs old

**Grade level**: 6th, 7th, and 8th

## ~

## Guiding ideas

Follow rules for [collegial discussions](http://www.corestandards.org/ELA-Literacy/SL/7/1/b/) and decision-making, track progress toward specific goals and deadlines, and define individual roles as needed. Pose questions that connect the ideas of several speakers and respond to others' questions and comments with relevant evidence, observations, and ideas. Acknowledge new information expressed by others, and, when warranted, qualify or justify their own views in light of the evidence presented.

#### Related Common Core ELA standards:

* [CCSS.ELA-LITERACY.SL.6](http://www.corestandards.org/ELA-Literacy/SL/6)
* [CCSS.ELA-LITERACY.SL.7](http://www.corestandards.org/ELA-Literacy/SL/7)
* [CCSS.ELA-LITERACY.SL.8](http://www.corestandards.org/ELA-Literacy/SL/8)

## 학생 학습 활동

This activity requires students to have the *Code Connection* app open and running with their *Minecraft Education Edition*. Graph paper is also useful for this activity, but it is not necessary. This is the first lesson in a 2-part series.

이 활동은 2개의 부분으로 이루어져 있습니다.:

* [Building a maze](#building-a-maze)
* [Solving the maze with AI](#solving-the-maze-with-ai)

### Building a maze

Have students get into groups of 2 or 3. If you are using graph paper, pass out the paper to each group. Have each group design a maze that is no bigger than 10 x 10 squares. Ensure that students have an entrance and an exit to their maze:

![예시 미로](/static/lessons/maze-ai.png)

#### Option 1

Have students create their maze in Minecraft by hand.

#### Option 2

Have students create their maze in Minecraft with code. For example, the code for the first two rows in the above maze would be:

```blocks
player.onChat("createMaze", function () {
    blocks.fill(
    blocks.block(Block.Stone),
    positions.create(0, 0, 0),
    positions.create(10, 1, 10),
    FillOperation.Replace
    )
    player.runChatCommand("row1")
    player.runChatCommand("row2")
})
player.onChat("row1", function () {
    blocks.place(blocks.block(Block.Air), positions.create(6, 0, 0))
    blocks.place(blocks.block(Block.Air), positions.create(6, 1, 0))
})
player.onChat("row2", function () {
    blocks.place(blocks.block(Block.Air), positions.create(4, 0, 1))
    blocks.place(blocks.block(Block.Air), positions.create(4, 1, 1))
    blocks.place(blocks.block(Block.Air), positions.create(5, 0, 1))
    blocks.place(blocks.block(Block.Air), positions.create(5, 1, 1))
    blocks.place(blocks.block(Block.Air), positions.create(6, 0, 1))
    blocks.place(blocks.block(Block.Air), positions.create(6, 1, 1))
})
```

### Solving the maze with AI

Have each group come up with a list of instructions to solve their maze. For example, these are steps to complete the maze coded in **Option 2** above. It begins with the agent standing at the *ENTRANCE* looking into the maze:

1. 앞으로 2만큼 이동
2. 오른쪽으로 회전
3. 앞으로 2만큼 이동
4. 왼쪽으로 회전
5. 앞으로 2만큼 이동
6. 왼쪽으로 회전
7. 앞으로 1만큼 이동
8. 오른쪽으로 회전
9. 앞으로 2만큼 이동

Have the students then code their agent to perform the actions. Ensure that the agent gets through their maze correctly.

**OPTIONAL**: Make it a competition! Who can design a maze that requires the most number of steps from an agent? The least number of steps?

## Performance expectations

Intended outcomes:

* This exercise can be completed in 1-3 class sessions, depending on the complexity of the mazes and whether students are designing algorithms.
* Students should be able to recognize the importance of abstraction and algorithms.

## 자료

[Artificial Intelligence - Part 2](/lessons/maze-ai-part2)