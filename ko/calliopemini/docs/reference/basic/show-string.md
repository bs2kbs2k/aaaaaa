# 문자열 출력

[LED 스크린](/device/screen)에 수(정수)를 출력합니다. 한 자리를 넘는 수는 왼쪽으로 슬라이드되며 나타나게 됩니다.

```sig
basic.showString("Hello!")
```

### 매개 변수

* `text` is a [String](/reference/types/string). It can contain letters, numbers, and punctuation.
* `interval` is an optional [Number](/reference/types/number). It means the number of milliseconds before sliding the [String](/reference/types/string) left by one LED each time. 화면 갱신 주기가 크면 클수록, 느리게 슬라이드됩니다.

### 예시:

다음 예시는 **Hello**를 출력합니다.:

```blocks
basic.showString("Hello")
```

To show what is stored in a [String](/reference/types/string) variable:

```blocks
let s = "Hi"
basic.showString(s)
```

### 다른 LED 출력 함수들

* [수(정수) 출력](/reference/basic/show-number)을 이용하면, [LED 스크린에](/device/screen) 숫자로 출력할 수 있습니다.
* 여러 장의 그룹으로 되어있는 사진을 LED 화면에 순서대로 하나씩 출력하려면, [애니메이션 출력](/reference/basic/show-animation)을 사용하면 됩니다.

### 참고 항목

[String](/reference/types/string), [show number](/reference/basic/show-number), [show animation](/reference/basic/show-animation)