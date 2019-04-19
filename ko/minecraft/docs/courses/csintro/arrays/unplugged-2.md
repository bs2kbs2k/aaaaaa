# Unplugged activity: Bubble Sort

In this activity, you will demonstrate one type of sorting method by using your own students. Have your students stand at the front of the room. If you or your students are curious to see what these different sorts look like in code, you can read through the following MakeCode version of the bubble sort algorithm. First you might want to try the unplugged activity to warm the students to the idea.

Materials needed:

* 10 sheets of paper numbered 1–10 in big letters

Have 10 students volunteer to stand up at the front of the classroom. Ask another student to volunteer to be the sorter.

Mix up the order of the papers and give each student a piece of paper with a number on it. They should hold the paper facing outward so their number is visible to the rest of the class. Each of these students represents a value in the array.

## Initial sort

Ask the sorter to place the students in order by directing them to move, one at a time, to the proper place. After the students are sorted, ask students the following questions:

* How did the sorter put you into the right order? 
* Did you see a pattern? 
* What strategy did the sorter use to put everyone in the right order?

Try to get students to be as precise as possible in explaining their thinking. Sometimes it helps to put the steps on the board, for example:

* First, she went to the first student in the line, then put him in the right place.
* Then she went down the line to each of the students and put them in the right place.
* Or, she went to the #1 student first, then the #2 student, and so on.

Ask for clarification when necessary: What does it mean when you say "put them in the right place"?

For example, to put someone in the right place means:

* Bring the person to the front of the line, and then compare that person’s number with the first person’s number. 
* If it’s larger, then move that person to the right. 
* Keep doing this as long as the person’s number is larger than the person on the right.

A good point to bring up is the fact that several mini tasks happen when you sort something. Pattern matching, comparing, and so on are all used. Without the proper instructions, there is no way for a computer to do this easily. Therefore, sorting is not always a simple task in computer science. However, if you think, test, and plan out your code, you can get the computer to sort some very complicated information.

## The bubble sort

One basic type of sorting algorithm is called a *bubble sort*, so named because the larger values tend to "bubble up" toward the end of the array.

### How to bubble sort

* Compare the first two students. 
* If the student on the right is smaller than the student on the left, they should swap places. 
* Then compare the second and third students. 
* If the student on the right is smaller than the student on the left, they should swap places. 
* When you reach the end, start over at the beginning again. 
* Continue in this way until you make it through the entire row of students without swapping anybody.

### In Pseudocode

1. Create a variable called `counter`.
2. Set the counter to zero.
3. Go through the entire array.
4. If the value you are considering is greater than the value to its right: >a. Swap them  
    b. Add one to `counter`
5. Repeat steps 2 through 4 as long as counter is greater than zero.

```blocks
let my_array: number[] = []
let temp = 0
let counter = 0
player.onChat("bubblesort", function () {
    counter = 1
    while (counter > 0) {
        counter = 0
        for (let n = 0; n <= 8; n++) {
            if (my_array[n] > my_array[n + 1]) {
                temp = my_array[n]
                my_array[n] = my_array[n + 1]
                my_array[n + 1] = temp
                counter += 1
            }
        }
    }
})
```

To have some fun, create two groups and race! You might even make one group use the bubble sort and have the other group use their own style. Then you could talk about the differences. If the bubble sort is slower, which it probably will be, you can again point to the fact that it may be slower but the directions to the computer are actually much simpler (compare two numbers, swap, repeat). The team using their own style, no doubt, relied on several other small decisions that would be difficult to convey to the computer in directions.

Computers are great at doing simple directions very quickly. Sorting should leverage this.