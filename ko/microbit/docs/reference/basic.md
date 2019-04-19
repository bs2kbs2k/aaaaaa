# 기본

@boardname@ 의 기본적인 함수/동작을 실행시킬 수 있습니다.

```cards
basic.showNumber(0);
basic.showIcon(IconNames.Heart);
basic.showLeds(`
. . . . .
. . . . .
. . # . .
. . . . .
. . . . .
`);
basic.showString("Hello!");
basic.clearScreen();
basic.forever(() => {

});
basic.pause(100);
basic.showArrow(ArrowNames.North);
```

## 참고 항목

[정수 출력](/reference/basic/show-number), [아이콘 출력](/reference/basic/show-icon), [LED 출력](/reference/basic/show-leds), [문자열 출력](/reference/basic/show-string), [LED 스크린 지우기](/reference/basic/clear-screen), [무한 반복 실행](/reference/basic/forever), [일시 중지(ms)](/reference/basic/pause), [화살표 출력](/reference/basic/show-arrow), [애니메이션 출력](/reference/basic/show-animation)