# 가져오기

배열에서 원하는 위치에 저장되어있는 값을 리턴합니다.

```block
let item = [""][0]
```

## 매개 변수

* **index**: 값을 가져올 위치를 의미하는 [수(정수)](/types/number).

## 리턴값

* 배열의 index 위치에 저장되어있는 값. 배열에 저장되어있는 값들은 모두 같은 [데이터형](/types)입니다.

### ~hint

**배열 범위 초과!**

만약, 이전까지 만들어져 있는 배열의 범위를 초과하는 위치(index)에서 값을 가져오려고 하면, [수](/types/number) `0`이 리턴됩니다.

### ~

## 예시

```blocks
let directions = ["North", "South", "East", "West"];
let path = "Turn to the " + directions[3];
```

## 추가 참고

[찾아보기](/reference/arrays/index-of)