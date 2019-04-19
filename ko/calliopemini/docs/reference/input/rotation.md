# 기울기

@boardname@ 가 기울여진 각도를 측정할 수 있습니다.

```sig
input.rotation(Rotation.Roll);
```

## ~hint

@boardname@ 보드에는 **가속도 센서가** 가 장치되어있기 때문에, @boardname@ 가 어떻게 움직이는지 알아낼 수 있습니다.

## ~

### 매개 변수

* `방향`. 기울기를 측정하고자하는 방향: `앞-뒤`, `좌-우`.

### 리턴값

* a [number](/reference/types/number) that means how much the microbit is tilted in the direction you say, from `0` to `360` degrees

### 예시: @boardname@ 수평계

다음은 @boardname@ 를 수평 상태로 만드는데 도움을 주는 예시 코드입니다. 수평이 맞춰지면 @boardname@ 에 스마일리 아이콘이 출력됩니다.

웹브라우저의 시뮬레이터에서는 마우스를 움직여 @boardname@ 를 기울일 수 있습니다.

```blocks
let pitch = 0;
basic.forever(() => {
    pitch = input.rotation(Rotation.Pitch);
    let roll = input.rotation(Rotation.Roll);
    if (Math.abs(pitch) < 10 && Math.abs(roll) < 10) {
        basic.showLeds(`
            . # . # .
            . . . . .
            . . . . .
            # . . . #
            . # # # .
            `);
    } else {
        basic.showLeds(`
            # . . . #
            . # . # .
            . . # . .
            . # . # .
            # . . . #
            `);
        }
    });
```

### 참고 항목

[가속도 센서 값](/reference/input/acceleration), [자기(나침반) 센서 각도](/reference/input/compass-heading)