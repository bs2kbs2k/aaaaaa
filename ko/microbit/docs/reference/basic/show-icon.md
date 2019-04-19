# 아이콘 출력

선택한 아이콘을 LED 스크린 화면에 출력합니다.

```sig
basic.showIcon(IconNames.Heart)
```

## 매개 변수

* `아이콘`, 화면에 출력할 아이콘
* `갱신 주기` (옵션), LED 스크린 화면을 갱신하는 시간. 단위 밀리 초. 기본 400 밀리 초.

## 예시

아래 프로그램은 `아이콘 출력` 함수를 이용해, 행복한 표정의 얼굴 아이콘을 표시하고 난 후, 1초 뒤에 슬픈 표정의 얼굴 아이콘을 출력합니다.

```blocks
basic.showIcon(IconNames.Happy)
basic.pause(1000)
basic.showIcon(IconNames.Sad)
```

## 참고 항목

[LED 출력](/reference/basic/show-leds)