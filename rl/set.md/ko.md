# set

배열에서 원하는 위치(index)에 원하는 값을 저장합니다.

```block
[""][0] = "item";
```

그 위치(index)에 이미 값이 저장되어있는 경우에는, 새로운 값으로 덮어쓰기 됩니다. 이전까지 만들어져있는 배열의 크기를 초과하는 위치(index)를 사용하면, 그 위치까지 데이터를 저장할 수 있도록 배열의 크기가 늘어납니다. 그렇게 그 위치에 값이 저장되면, 그 사이에 있는 값들은 모두 `0`으로 채워집니다.

## 매개 변수

* **index**: 값을 저장할 위치를 의미하는 [수(정수)](/types/number).

## 예시

생각을 바꿔서, 여러 색 중 갈색(brown)을 녹색(green)으로 변경합니다.

```blocks
let favColors = ["orange", "blue", "red", "brown", "yellow"];
favColors[3] = "green";
```

## 참고 항목

[원하는 위치에 삽입하기](/reference/arrays/insert-at)