# 찾아보기

Get the index (position) of the first element in the array that matches a search item.

```sig
["hello"].indexOf("hello")
```

## 매개 변수

* **item**: the item to find somewhere in the array.
* **from**: a [number](/types/number) which is the position in the array to begin the search. You use this if you want the search to start at someplace past `0`, the first position.

## 리턴값

* a [number](/types/number) which is the position in the array where the element is found. This number is `-1` if a matching element isn't found anywhere in the array.

## 예시

Get the index of "popcorn" in a list of movie treats.

```blocks
let movieSnacks = ["mints", "cola", "pretzel", "popcorn", "peanuts"];
let popcorn = movieSnacks.indexOf("popcorn");
```