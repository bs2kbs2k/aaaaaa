# 정수 출력

[LED 스크린](/device/screen)에 수를 출력합니다. 한 자리를 넘는 수는 왼쪽으로 슬라이드되며 나타나게 됩니다.

```sig
basic.showNumber(2)
```

## 매개 변수

* `값`, [수(정수)](/types/number).
* 왼쪽으로 슬라이드 되는 화면 `갱신 주기`는 옵션 [수(정수)](/types/number). 화면 갱신 주기는, LED 상태가 왼쪽으로 슬라이드 되어 움직이도록 할 때, 왼쪽으로 움직일 때 까지 유지하는 시간(ms) `값`을 의미합니다. 화면 갱신 주기가 크면 클수록, 느리게 슬라이드됩니다.

## 예시:

수(정수) 10을 출력하기 위해서는:

```blocks
basic.showNumber(10)
```

어떤 변수에 저장되어있는 값(수)을 출력하기 위해서는:

```blocks
let x = 1
basic.showNumber(x)
```

## 예시: 5까지 카운트하기

다음은 [반복(for)](/blocks/loops/for) 실행 구조를 이용해서, `0` 부터 `5` 까지 스크린 화면에 순서대로 출력하는 예시입니다.:

```blocks
for (let i = 0; i < 6; i++) {
    basic.showNumber(i)
    basic.pause(200)
}
```

## 다른 LED 출력 함수들

* [문자열(텍스트)](/types/string)을 LED 스크린 화면에 출력하려면, [문자열 출력](/reference/basic/show-string)을 사용하면 됩니다.
* 여러 장의 그룹으로 되어있는 사진을 LED 화면에 순서대로 하나씩 출력하려면, [애니메이션 출력](/reference/basic/show-animation)을 사용하면 됩니다.

## 참고 항목

[문자열 출력](/reference/basic/show-string), [애니메이션 출력](/reference/basic/show-animation), [수(정수)](/types/number), [계산](/blocks/math)