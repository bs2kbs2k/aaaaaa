# Unplugged activity: Paper AI

Tell the students that they are going to play a game that they are probably all so familiar with that they may have stopped playing it altogether because it’s not a challenge anymore. It’s Tic-Tac-Toe!

## Form some AI rules

1. Have the students pair with a classmate and play a few rounds of tic-tac-toe. They usually enjoy this since for most of them it has been a while since they’ve played.

2. Ask the students how much they thought about the decisions they were making while they played. Did they think when making decisions about where to place their mark next and how their decisions may change depending on the other player’s moves? For most students, since they are so familiar with the game, they feel like they aren’t thinking too much about their moves.

3. Have them play a few more rounds of tic-tac-toe, but this time they should try to be aware of their thinking. Why are they making the moves that they are, and how do their opponent’s moves affect their moves?

4. Ask them to share some of the thinking that went into deciding where to place their next mark after they play a few more rounds.

5. Challenge them to come up with a list of rules/strategies that anyone could follow to win at tic-tac-toe. Tell them they can use if-else structures to describe their rules. What they’re writing is pseudocode… a mix of English and code.

6. To get them going with their list of rules, as a class, have them suggest a rule for the very first move. Most will say, if the center spot is open, place your mark in the center spot.

7. Ask them to think about their next move, and then the one after that... continuing their list of rules/strategies until they think their rules would help anyone win every time.

8. This is usually where the students realize just how much thinking actually goes into their decision making. This activity really challenges most students, even those that thought at first it would be easy!

9. Have each student swap their finished list of rules with their classmate and play a few more rounds of tic-tac-toe against each other. The important difference in these rounds is that each student must use only the set of rules written by their classmate to determine their next move. They may not use their own rules or strategies. They enjoy this activity and they begin to realize more about the game and what it takes to write rules that result in a win every time.

10. Ask them to imagine what it takes to program a computer to play checkers or chess!

**Optional challenge:** Write a list of rules/strategies to play connect four. Try it out with a classmate.

## Sample AI rules for Tic-Tac-Toe

Here are some Sample AI rules for Tic-Tac-Toe:

**Move 0:**

* Place your mark in the center.

**Move 1:**

* If opponent places their mark adjacent to center, then place your next mark in a corner. 
* Else place your mark adjacent to center.

**Move 2:**

* If there are two of your marks in a row, column, or diagonal and the third space in that row, column, or diagonal is an empty space, place your mark there for the win.
* Else, place your mark in the other corner.

**Move 3 and beyond:**

* If there are two of your marks in a row, column, or diagonal and the third space in that row, column, or diagonal is an empty space, place your mark there for the win. 
* Else, if your opponent has two of their marks in a row, column, or diagonal and the third space in that row, column, or diagonal is an empty space, place your mark there for the block. 
* Else, go in any empty space.