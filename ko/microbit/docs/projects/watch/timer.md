# Countdown Timer

### ~avatar avatar

@boardname@ 손목시계를 카운트다운 타이머로 만들어봅시다.

### ~

## 활동 소요시간: ~10분

## 시간 저장을 위한 변수 만들기

남은 시간을 기록하기 위해서 변수가 하나 필요합니다.

1. **기본** 카테고리에서 `||basic:on start||` 블록을 가져옵니다.
2. 자, 그 다음에 **변수** 카테고리에서 `변수 만들기` 를 누릅니다. 변수의 이름을 `seconds` 로 바꿉니다. `||variables:set to||` 블록을 가져온 후, 드롭다운 메뉴를 이용해 변수 이름을 `seconds` 로 바꿉니다. `||basic:on start||` 안으로 변수들을 넣습니다.

```blocks
let seconds = 0
```

## 버튼으로 시간 설정하기

손목시계에 시간을 설정할 수 있어야 합니다. 버튼들을 사용해서 10 초, 1 초 씩 추가할 수 있도록 할 것입니다. 한 버튼으로 `10` 초를 추가하고, 다른 버튼으로는 `1` 초를 추가할 수 있도록 할 것입니다.

### 10 초씩 설정하기

`A` 버튼을 누르면, 카운트다운 시간에 `10` 초씩 추가되도록 할 것입니다. 버튼을 한 번 누를 때마다, `seconds` 변수에 저장된 값이 `10` 만큼씩 증가될 것입니다.

1. **입력** 카테고리에서, `||input:on button pressed||` 을 찾아 가져옵니다.
2. `||logic:if then||` 블록을 **논리** 카테고리에서 가져와 `||input:on button pressed||` 블록 안에 넣습니다.
3. 같은 **논리** 카테고리에서, `||logic:0 < 0||` 블록을 가져온 후 `참/거짓` 조건 부분에 붙입니다.
4. 조건식의 왼쪽에 있는 `0` 을 `seconds` 변수로 바꿉니다. 조건식의 오른쪽에 있는 `0` 을 `50` 으로 바꿉니다. 50 은 1분보다 작은 10 초 단위의 최대 시간입니다.
5. `||logic:then||` 부분에, `||variables:change by||` 블록을 집어 넣습니다. 드롭다운 메뉴를 눌러 `seconds` 변수를 선택하고, 오른쪽에 있는 `0` 을 `10` 으로 바꿉니다.
6. `||basic:show number||` 블록을 `||variables:change by||
 블록 아래에 추가`하세요. 값을 변경할 변수를 `seconds` 로 바꿉니다. 그 아래에 `||basic:clear screen||` 를 붙여넣습니다.

```blocks
let seconds = 0;
input.onButtonPressed(Button.A, () => {
    if (seconds < 50) {
        seconds += 10;
        basic.showNumber(seconds)
        basic.clearScreen()
    }
})
```

### 1 초씩 설정하기

이제, `B` 버튼을 누르면, 카운트다운 시간에 `1` 초씩 추가되도록 할 것입니다. 버튼을 한 번 누를 때마다, `seconds` 변수에 저장된 값이 `1` 만큼씩 증가될 것입니다.

1. **입력** 카테고리에서, `||input:on button pressed||` 을 찾아 가져옵니다.
2. `||logic:if then||` 블록을 **논리** 카테고리에서 가져와 `||input:on button pressed||` 블록 안에 넣습니다.
3. 같은 **논리** 카테고리에서, `||logic:0 < 0||` 블록을 가져온 후 `참/거짓` 조건 부분에 붙입니다.
4. 조건식의 왼쪽에 있는 `0` 을 `seconds` 변수로 바꿉니다. 조건식의 오른쪽에 있는 `0` 을 `60` 으로 바꿉니다. 60 초는 1분의 최대 초 입니다.
5. `||logic:then||` 부분에, `||variables:change by||` 블록을 집어넣습니다. 드롭다운 메뉴에서 `seconds` 변수를 선택합니다.
6. `||basic:show number||` 블록을 `||variables:change by||
 블록 아래에 추가`하세요. 값을 변경할 변수를 `seconds` 로 바꿉니다. 그 아래에 `||basic:clear screen||` 를 붙여넣습니다.

```blocks
let seconds = 0;
input.onButtonPressed(Button.B, () => {
    if (seconds < 60) {
        seconds += 1;
        basic.showNumber(seconds)
        basic.clearScreen()
    }
})
```

## 흔들어서 시간 보기

자 이제, 타이머 시간이 흘러가면서 남은 시간을 출력하도록 할 것입니다. 남은 시간을 출력하는 것은 손목시계를 흔들었을 때로 하면 됩니다!

1. `||input:on shake||` 블록을 입력 카테고리에서 찾아, 코드 편집화면으로 가져옵니다.
2. `||loops:while||` 블록을 **반복** 카테고리에서 찾아, `||input:on shake||` 블록 안에 집어넣습니다. `참(true)` 조건을 `||logic:0 < 0||` 조건식으로 바꿉니다. **논리** 카테고리에서 찾을 수 있습니다. `<` 를 `>` 로 바꿉니다. 왼쪽의 `0` 값을 `seconds` 변수로 바꿉니다.
3. 다른 `||basic:show number||` 블록을 `||loops:while|| 블록의 안쪽에` 넣습니다. 왼쪽의 `0` 값을 `seconds` 변수로 바꿉니다. `||basic:pause||` 를 그 아래에 붙이고, 시간을 `1000` 밀리초로 설정합니다. 이렇게하면, **1000** 밀리초 동안 시간이 카운트다운되고, 1초마다 반복되면서 카운트다운되는 것과 같습니다.
4. 남은 카운트다운 초를 바꾸기 위해서는, `||variables:change by||` 를 가져와 `||loops:pause||` 아래에 붙이면 됩니다. `||math:0 - 0||` 블록을 **계산** 카테고리에서 찾아 `||variables:change by||` 의 증가값 부분에 넣습니다. 오른쪽 `0` 값을 `1` 로 설정합니다.

```blocks
let seconds = 0;
input.onGesture(Gesture.Shake, () => {
    while (seconds > 0) {
        basic.showNumber(seconds);
        basic.pause(1000);
        seconds -= 1;
    }
})
```

## 알람 설정하기!

몇 개의 `||basic:show icon||` 블록들을 `||loops:while||` 블록의 아랫쪽에 넣어, 제한시간이 다 흘렀을 때 알람을 표시하도록 만들어보세요! 다이아몬드 모양과 'X' 모양을 더 추가해 봅니다.

```blocks
let seconds = 0;
input.onGesture(Gesture.Shake, () => {
    while (seconds > 0) {
        basic.showNumber(seconds);
        basic.pause(1000);
        seconds -= 1;
    }
    basic.showIcon(IconNames.Diamond)
    basic.showIcon(IconNames.SmallDiamond)
    basic.showIcon(IconNames.No)
})
```

## 모두 완료했습니다!

참 잘했습니다! 이제 타이머 코드가 만들어졌습니다. `|download|` 를 눌러 @boardname@ 에서 실행시켜보세요. 손목시계를 흔들면, 설정한 시간으로 카운트다운이 시작됩니다.

처음에는, 0 초로 설정되어 있습니다. 10 초를 추가하기 위해서는 **A** 버튼을 누르면 되고, 1 초를 추가하기 위해서는 **B** 버튼을 누르면 됩니다.