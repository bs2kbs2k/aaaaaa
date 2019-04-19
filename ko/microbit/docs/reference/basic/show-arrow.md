# 화살표 출력

선택한 화살표를 LED 스크린 화면에 출력합니다.

```sig
basic.showArrow(ArrowNames.North)
```

## 매개 변수

* `방향`. 출력할 화살표의 방향
* `갱신 주기` (옵션), LED 스크린 화면을 갱신하는 시간. 단위 밀리 초. 기본 400 밀리 초.

## 예시

다음 예시는 8 개의 모든 화살표를 출력해 보여줍니다.

```blocks
for (let index = 0; index <= 7; index++) {
    basic.showArrow(index)
    basic.pause(300)
}
```

## 참고 항목

[아이콘 출력](/reference/basic/show-icon), [LED 출력](/reference/basic/show-leds)