# Arrays

In Lesson 4, you discovered variables, which are used to store information. An array is a series of places to store things. You can think of it like many variables in one place. You can store several items under the same name and you only need that one name to find the information. This information could be a list of items, a row of mailboxes, or a train of container boxes. for example. The information in the array is all similar.

For example, maybe we want to store what each of these mailboxes has in it.

Search the web for a row of mailboxes on the street.

If you wanted to save information about the preceding mailboxes and used variable, you would need to make several variables with names like `Mailbox0`, `Mailbox1`, and so on.

![Make Many Variables](/static/courses/csintro/arrays/overview-point1.png)

This is time consuming because you have to type a lot, and it is inefficient when you want to later get that information back. This is where arrays help in a big way.

![Use One Array](/static/courses/csintro/arrays/overview-point2.png)

By using one array and one name, you can store all the information you need. Then you just use the one name, "Mailboxes," and the number or "key" of the mailbox you want. The keys in this example are `0`, `1`, `2`, `3`, `4`, and `5`. Sometimes the term index is used too. The key or index is the number of the box holding the information you want.

Therefore, when you have a lot of variables to deal with, it’s more convenient to use an array. Also, arrays are handy when you don’t know ahead of time how many variables you are going to need.

## Array indexes

The location of a particular item in the array is known as its *index*. By default, arrays start at an index of `0`. The first item in an array has an index of `0`, the next one has an index of `1`, and so on.

The length of an array is the same as the number of items in the array.

For example, if there are six mailboxes, with indexes from `0` to `5`. The length of this array is 6.

Search the web for a row of mailboxes on the street.

## Array elements

In MakeCode, you can store different [types](/types) in an array:

* Numbers
* Text
* Chickens
* Positions
* Blocks
* Zombies

You can add objects to an array, remove them, and count the number of things in the array at any given time. You can even reverse their order in the array with a single command. Arrays are a convenient and powerful way to work with lots of items at once.

## Sort Array Values

After you start saving lots of different values in an array, you will probably want to have some way to sort those values. In computer science, there are certain common strategies, or algorithms, for sorting a collection of values. Understanding how those different sorting algorithms work is an important part of computer science. As you progress in your coding knowledge. you will learn about these algorithms, as well as their relative efficiency. Some of the different sorting algorithms include:

* Selection sort
* Insertion sort
* Quick sort
* Merge sort
* Bubble sort
* Shell sort

Search the web for a video that visually displays a computer sorting information with different types of sorting algorithms.

In this chapter, you will create an instant zoo, and fill it with animals from your array. You will also create a warp belt that allows you to save locations on your map and instantly teleport to them. Finally, you will use blocks in a new way with the power of arrays.