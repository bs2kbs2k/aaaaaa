# 정수 출력

Show a number on the screen at the line you select.

```sig
brick.showNumber(0, 1);
```

## 매개 변수

* **value**: a [number](/types/number) to show on the brick's screen.
* **line**: The line number on the screen where the value is displayed. The line numbers for the screen start with line `1`.

## 예시

Show the number `1000` on the screen.

```blocks
brick.showNumber(1000, 1);
```

## 참고 항목

[show string](/reference/brick/show-string), [show value](/reference/brick/show-value)