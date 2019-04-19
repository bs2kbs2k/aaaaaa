# Show Animation

이미지(사진) 프레임 그룹을 순서대로 [LED 스크린](/device/screen)에 출력합니다. 원하는 갱신 주기(시간) 만큼씩 일시 중지되며 각 프레임이 출력됩니다.

```sig
basic.showAnimation(`
. . # . . . # # # . . # # # .
. # # . . . . . # . . . . # .
. . # . . . . # . . . # # # .
. . # . . . # . . . . . . # .
. . # . . . # # # . . # # # .
`)
```

### 매개 변수

* `leds` is a [String](/reference/types/string) that shows which LEDs are on and off, in groups one after another.
* `interval` is an optional [Number](/reference/types/number). It means the number of milliseconds to pause after each image frame.

### 예시: 이미지 프레임 그룹 애니메이션 출력하기

다음 애니메이션에는 폭(너비)이 15 크기에 3 개의 프레임이 있는 것입니다. 각 프레임은 @boardname@ 스크린 배치 처럼 너비가 5 칸 입니다.

```blocks
basic.showAnimation(`
. . # . . . # # # . . # # # .
. # # . . . . . # . . . . # .
. . # . . . . # . . . # # # .
. . # . . . # . . . . . . # .
. . # . . . # # # . . # # # .
`)
```

### ~hint

애니메이션이 너무 빠르게 지나가면, `갱신 주기(시간)` 값을 더 크게 설정하면 됩니다.

### ~

### 예시: 프레임 애니메이션 잠시 중단시키기

다음 예시는, 6개의 프레임을 500 밀리초 마다 잠시 중지시켜가며 출력하는 예시입니다.

다음 애니메이션에는 폭(너비)이 30 크기에 6 개의 프레임이 있는 것입니다. 각 프레임은 @boardname@ 스크린 배치 처럼 너비가 5 칸 입니다.

```blocks
basic.showAnimation(`
. . . . . # . . . . . . . . . . . . . # . . . . . # . . . .
. . # . . . . . . . . . # . . . . . . . . . # . . . . . . .
. # . # . . . # . . . # . # . . . # . . . # . # . . . # . .
. . # . . . . . . . . . # . . . . . . . . . # . . . . . . .
. . . . . . . . . # . . . . . # . . . . . . . . . . . . . #
`, 500)
```

### ~hint

[무한 반복 실행](/reference/basic/forever)을 사용하면, 애니메이션을 계속해서 출력할 수 있습니다.

### ~