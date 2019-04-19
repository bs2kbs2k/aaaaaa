# 배열

*배열*은 여러 개의 데이터 아이템들을 순서대로 연결해 저장할 수 있는, 간단한(기본적인) 데이터형입니다.

## #intro

배열은 데이터 아이템들이 연속적으로 연결되어 저장된 리스트로서, 그 안에 수(정수), 불(참/거짓) 값, 문자열을 저장할 수 있습니다. Arrays have a length which is the number of items they contain. 배열에 저장되어있는 데이터들을 가져오고, 값을 바꿀 수 있습니다. You find items in an array by knowing their positions.

이 프로그래밍언어에서는 배열의 크기를 바꿀 수 있습니다. 배열의 크기를 늘이거나 줄일 수 있습니다. 배열에 저장되어있는 데이터 아이템을 제거하거나, 새로운 데이터를 추가할 수도 있습니다.

## 배열 만들기

배열은 데이터 아이템들을 나열하며, 초기화해서 만들 수 있습니다.

```block
let scores = [9, 8, 3, 5, 6, 8];
```

Here the array automatically becomes an array of [numbers](/types/number) because it was created with items that are numbers.

[문자열](/types/string)과 같은 다른 데이터형 배열도 만들어 사용할 수 있습니다.

```block
let directions = ["East", "North", "South", "West"];
```

If you want to create an array with no items in it yet (empty array), you have to tell what type the array should be. This is because there are no items in it that automatically decide the type.

```typescript
let scores: number[] = [];
```

## 배열에 저장되어있는 데이터 아이템들

When an item is added to an array it becomes an *element* of the array. Array elements are found using an *index*. 참조번호는 배열에 저장되어있는 위치, 배열에 저장되어있는 요소들의 *순서(order)*를 의미합니다. The positions in an array begin with the index of `0`. The first place in the array is `0`, the second place is `1`, and so on.

```block
let scores = [9, 8, 3, 5, 6, 8];
let firstScore= scores[0];
let secondScore = scores[1];
```

## 배열의 크기(길이)

배열은 크기(길이)가 있습니다. 배열의 마지막에 저장되어있는 데이터 요소의 저장위치(참조번호, index)는 *배열의 크기(길이)-1*이 됩니다. Indexes begin with `0` so the last element's index is one less than the array length.

```block
let directions = ["East", "North", "South", "West"];
let count = directions.length;
```

## 고급

Arrays are a very useful way to collect and organize information. There are more advanced operations and functions you can use on arrays.

아래는 어떤 수를 배열의 중간에 삽입해 끼워넣는 [**insertAt**](/reference/arrays/insert-at)을 사용한 예시입니다.

```block
let scores = [8, 5, 9, 3, 2, 4];
scores.insertAt(3, 1);
```

## #examples

### 참고 항목 #seealso