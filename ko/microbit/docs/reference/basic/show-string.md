# 문자열 출력

Show a string on the [LED screen](/device/screen). It will scroll to left if it's bigger than the screen.

```sig
basic.showString("Hello!")
```

## 매개 변수

* `텍스트`. [문자열](/types/string). 문자, 수, 기호들이 포함될 수 있습니다.
* `갱신 주기` 옵션. [수(정수)](/types/number). 화면 갱신 주기는, [문자열](/types/string)이 LED 에서 왼쪽으로 슬라이드 되어 움직이도록 할 때, 다음 LED 위치로 움직이기 전까지 일시 중지하는 시간(ms)을 의미합니다. 화면 갱신 주기가 크면 클수록, 느리게 슬라이드됩니다.

## 예시:

다음 예시는 **Hello**를 출력합니다.:

```blocks
basic.showString("Hello")
```

[문자열형](/types/string) 변수에 저장되어있는 값을 출력하는 예시:

```blocks
let s = "Hi"
basic.showString(s)
```

## 다른 LED 출력 함수들

* [수(정수) 출력](/reference/basic/show-number)을 이용하면, [LED 스크린에](/device/screen) 숫자로 출력할 수 있습니다.
* 여러 장의 그룹으로 되어있는 사진을 LED 화면에 순서대로 하나씩 출력하려면, [애니메이션 출력](/reference/basic/show-animation)을 사용하면 됩니다.

## 참고 항목

[문자열](/types/string), [수 출력](/reference/basic/show-number), [애니메이션 출력](/reference/basic/show-animation)