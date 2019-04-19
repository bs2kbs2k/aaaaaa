# Compass

## ~avatar avatar

환영합니다! 이 안내 튜토리얼은 @boardname@ 가 가리키는 방향을 출력하는 프로그램 스크립트를 작성하는 방법을 안내할 것입니다. 자 이제 시작해보세요!

## ~

![](/static/mb/projects/a5-compass.png)

@boardname@ 의 자기(나침반) 센서가 가리키는 방향을 출력합니다.

## 단계 1

자기(나침반) 센서가 가리키는 방향을 계속해서 업데이트해주는, 반복 실행 구조를 만듭니다.

```blocks
basic.forever(() => {

})
```

## 단계 2

@boardname@ 보드가 가리키는 방향을 읽어, `degrees` 변수에 저장합니다.

```blocks
basic.forever(() => {
    let degrees = input.compassHeading()
})
```

## 단계 3

`degrees` 변수에 저장된 값이 `45` 도 보다 작거나 `315` 도 보다 크면, 자기(나침반) 센서가 거의 북쪽(North)을 가리키고 있는 것입니다. @boardname@ 에 `N` 을 출력합니다.

```blocks
basic.forever(() => {
    let degrees = input.compassHeading();
    if (degrees < 45 || degrees > 315) {
        basic.showString("N");
    }
});
```

## 단계 4

만약 `degrees` 변수에 저장된 값이 `135` 보다 작으면, @boardname@ 의 자기(나침반) 센서가 거의 **동쪽(East)**을 가리키고 있는 것입니다. @boardname@ 에 `E` 를 출력합니다.

```blocks
basic.forever(() => {
    let degrees = input.compassHeading();
    if (degrees < 45 || degrees > 315) {
        basic.showString("N");
    }
    else if (degrees < 135) {
        basic.showString("E");
    }
});
```

## 단계 5

만약 `degrees` 변수에 저장된 값이 `225` 보다 작으면, @boardname@ 의 자기(나침반) 센서가 거의 **남쪽(South)**을 가리키고 있는 것입니다. @boardname@ 에 `S` 를 출력합니다.

```blocks
basic.forever(() => {
    let degrees = input.compassHeading();
    if (degrees < 45 || degrees > 315) {
        basic.showString("N");
    }
    else if (degrees < 135) {
        basic.showString("E");
    }
    else if (degrees < 225) {
        basic.showString("S");
    }
});
```

## 단계 6

위의 범위가 아니면, @boardname@ 의 자기(나침반) 센서가 거의 **서쪽(West)**을 가리키고 있는 것입니다. @boardname@ 에 `W` 를 출력합니다.

```blocks
basic.forever(() => {
    let degrees = input.compassHeading();
    if (degrees < 45 || degrees > 315) {
        basic.showString("N");
    }
    else if (degrees < 135) {
        basic.showString("E");
    }
    else if (degrees < 225) {
        basic.showString("S");
    }
    else {
        basic.showString("W");
    }
});
```