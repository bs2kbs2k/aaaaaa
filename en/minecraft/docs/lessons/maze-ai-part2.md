# Artificial intelligence - Part 2

Students collaboratively write AI to solve any maze.

## Learning Objectives

Understand the importance of dividing up work, collaborating with others, designing before building, and adjusting designs based on new input

## ~ hint

#### Applicability

**Skill areas**: Speaking and Listening, Collaboration, Roles

**Ages**: 11-13 yrs old

**Grade level**: 6th, 7th, and 8th

## ~

## Guiding Ideas

Follow rules for [collegial discussions](http://www.corestandards.org/ELA-Literacy/SL/7/1/b/) and decision-making, track progress toward specific goals and deadlines, and define individual roles as needed. Pose questions that connect the ideas of several speakers and respond to others' questions and comments with relevant evidence, observations, and ideas. Acknowledge new information expressed by others, and, when warranted, qualify or justify their own views in light of the evidence presented.

#### Related Common Core ELA standards:

* [CCSS.ELA-LITERACY.SL.6](http://www.corestandards.org/ELA-Literacy/SL/6)
* [CCSS.ELA-LITERACY.SL.7](http://www.corestandards.org/ELA-Literacy/SL/7)
* [CCSS.ELA-LITERACY.SL.8](http://www.corestandards.org/ELA-Literacy/SL/8)

## Student activities

This activity requires students to have the *Code Connection* app open and running with their *Minecraft Education Edition*. Graph is also useful for this activity, but it is not necessary. This is the second part in a 2-part series on Artificial Intelligence.

This activity consists of 2 parts:

* [Algorithm to solve any maze](#algorithm-to-solve-any-maze)
* [Solving any maze with AI](#solving-any-maze-with-ai)

### Algorithm to solve any maze

Have students get into groups of 2-3. If you are using graph paper, pass out copies of mazes made in the previous class section to each group. Mazes should look something like this:

![Example maze](/static/lessons/maze-ai.png)

Have students write the algorithm to solve **each** maze individually first. For example:

1. Forward 2
2. Turn Right
3. Forward 2
4. Turn Left
5. Forward 2
6. Turn Left
7. Forward 1
8. Turn Right
9. Forward 2

Now, have students extrapolate a generic algorithm that could be used to solve any of the mazes they were given.

### Solving any maze with AI

Lead a class discussion on some of the generic algorithms that were created, then allow students to turn those algorithms into code.

Have them use logic with their agent to allow their agent to solve any maze. For example, if the “Exit” is identified with a gold block on the ground, the following code should be able to solve the maze:

```blocks
player.onChat("solveMaze", function () {
    while (agent.inspect(AgentInspection.Block, SixDirection.Down) != blocks.block(Block.GoldBlock)) {
        while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Forward, 1)
    }
})
```

Finally, have each student enter each maze within the world and test their algorithm on each maze. Allow them to adjust their algorithm as needed.

Lead a class discussion on the final algorithms that were created. There should be a general consensus.

### ~ hint

**Maze solution cases**

Some maze topologies may not lend themselves to a general algorithmic solution. Students might construct mazes with intersecting paths which cause the agent to circle around inside the maze without ever arriving at the EXIT. While this situation doesn't result in a solution to the maze, it does provide an opportunity for further discussion. You may wish to lead a follow-on discussion about how a simple step-based solution is not sufficient to solve every maze in general.

Alternatively, you can review the paths in each student's maze. Have them adjust the maze, if necessary, to ensure a finite solution with the agent eventually arriving at the EXIT. Explain why the change was necessary in order for the agent to finish the maze.

### ~

## Performance Expectations

Intended outcomes:

* This exercise can be completed in 1-2 class sessions, depending on the complexity of the mazes and whether students are designing algorithms.
* Students should be able to recognize the importance of abstraction and algorithms.

## Resources

[Artificial Intelligence - Part 1](/lessons/maze-ai-part1)