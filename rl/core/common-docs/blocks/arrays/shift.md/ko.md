# shift

Remove and return the first element from an array.

```sig
[""].shift()
```

The first element in the array is removed, so the array becomes smaller by one element.

If you have an array with 4 numbers, like 1, 2, 3, and 4, you remove the first number from the array by *shifting* it from the front. To shift the number from the array in blocks, do this:

```block
let thoseNumbers = [1, 2, 3, 4];
let firstNumber = thoseNumbers.shift();
```

## 리턴값

* the first element in the array.

## 예시

Find out how many odd numbers there are as you remove all the numbers from a list.

```blocks
let odds = 0;
let ints = [45, 78, 98, 3, 5, 6, 12, 643, 0, 34, 4];
while (ints.length > 0) {
    if ((ints.shift() % 2) > 0) {
        odds++;
    }
}
```

## 참고 항목

[unshift](/blocks/arrays/unshift), [pop](/blocks/arrays/pop)