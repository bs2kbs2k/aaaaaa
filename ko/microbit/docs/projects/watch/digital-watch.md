# Digital Watch

### ~avatar avatar

여러분이 만든 손목시계에 시간의 힘을 넣어보세요. 여러분의 @boardname@ 를 프로그래밍해서 진짜 시계처럼 움직이도록 만들어보세요.

### ~

## 활동 소요시간: ~20분

## 시간 저장을 위한 변수 만들기

시간을 기록하고 추적하기 위한 목적 등을 위해, 몇 가지 변수를 더 만들어야 합니다.

1. **기본** 카테고리에서 `||basic:on start||` 블록을 가져옵니다.
2. 자, 그 다음에 **변수** 카테고리에서 `변수 만들기` 를 누릅니다. 변수의 이름을 `hours` 로 바꿉니다. `||variables:set to||` 블록을 가져온 후, 드롭다운 메뉴를 이용해 변수 이름을 `hours` 로 바꿉니다. `||basic:on start||` 안으로 변수들을 넣습니다.
3. 같은 방법으로 4 번 더 반복 하면서 `minutes`, `time`, `adjust`, `ampm` 을 더 만듭니다.
4. 이제, `||variables:set to||` 블록으로 `time` 변수의 값을 바꿀 수 있도록 하면서, **문자열** 카테고리에서 `" "` 을 가져와 `0` 대신에 넣습니다.
5. `ampm` 변수는, `0` 을 `거짓(false)` 으로 바꿉니다. **논리** 카테고리에서 찾을 수 있습니다. 

```blocks
let hours = 0
let minutes = 0
let adjust = 0
let time = ""
let ampm = false
```

## 시간을 표시해 봅니다.

자, 이제 디스플레이를 통해 시간을 출력하는 방법을 만들어봅시다. 아직 시간 정보를 가지고 있지는 않지만, 시간형식처럼 출력할 수 있는지 살펴볼 수 있습니다.

1. **입력** 카테고리에서 `||input:on shake||` 블록을 가져옵니다. 손목시계를 흔들면 시간이 출력되도록 만들것입니다.
2. 다른 `||variables:set to||` 블록을 가져온 후, 그 안에 `||input:on shake||` 블록을 넣습니다. 값을 변경할 변수를 `time` 로 바꿉니다.
3. `0` 을 `||text:join||` 로 바꿉니다. **문자열** 카테고리에서 찾을 수 있습니다. 다른 `||text:join||` 을 가져온 후, 먼저 가져온 첫 번째 `||text:join||` 블록의 두 번째 슬롯에 넣습니다.
4. `" "` 의 값을 바꿉니다. 첫 번째 `||text:join||` 에서 `hours` 변수로 바꿉니다. 두 번째 `||text:join||` 의 첫 번째 슬롯의 문자열을 `":"` 로 바꿉니다. 그리고, 두 번째 `||text:join||` 의 마지막 슬롯에 있는 값을 `minutes` 변수로 바꿉니다.
5. 마지막으로, `||basic:show string||` 블록 아래에 `||variables:set to||` 블록을 넣으세요. 그 다음에 안에 있는 텍스트를 `time` 변수로 바꾸어 넣으세요.
6. 작성한 프로그램 코드를 @boardname@ 로 업로드 한 후, 흔들어보세요. LED 스크린 화면에 "0:0" 가 출력되는 것이 보이시나요?

```blocks
let time = ""
let minutes = 0
let hours = 0
input.onGesture(Gesture.Shake, () => {
    time = hours + (":" + minutes);
    basic.showString(time);
})
```

## 버튼으로 시간 설정하기

시계마다 시간을 설정하는 방법이 있습니다. 우리는 버튼들을 이용해서 시간을 맞추도록 할 것입니다. 한 버튼으로는 시간을 설정하고 다른 버튼으로는 분을 설정할 수 있도록 할 것입니다.

### 시간 설정하기

손목시계의 시간을 맞출 수 있도록 해봅시다.

1. **입력** 카테고리에서, `||input:on button pressed||` 을 찾아 가져옵니다.
2. `||logic:if then else||` 블록을 **논리** 카테고리에서 가져와 `||input:on button pressed||` 블록 안에 넣습니다.
3. 같은 **논리** 카테고리에서, `||logic:0 < 0||` 블록을 가져온 후 `참/거짓` 조건 부분에 붙입니다.
4. 조건식의 왼쪽에 있는 `0` 을 `hours` 변수로 바꿉니다. 조건식의 오른쪽에 있는 `0` 을 `23` 으로 바꿉니다. 시간은 최대 23 시까지 가능하기 때문입니다.
5. `||logic:then||` 부분에, `||variables:change by||` 블록을 집어넣습니다. 드롭다운 메뉴에서 `hours` 변수를 선택합니다.
6. `||logic:else||` 부분에, `||variables:set to||` 블록을 집어넣습니다. 드롭다운 메뉴에서 `hours` 변수를 선택하고 `0` 인 상태로 둡니다.

```blocks
let hours = 0;
input.onButtonPressed(Button.A, () => {
    if (hours < 23) {
        hours += 1;
    } else {
        hours = 0;
    }
})
```

### 분 설정하기

분을 설정하는 것은 몇 가지만 제외하면 시간을 설정하는 방법과 거의 같습니다.

1. 쉽게 만들려면, `||input:on button pressed||` 블록을 오른쪽 클릭한 후 나타나는 **복사** 메뉴를 누르면 됩니다. 이렇게 하면 어떤 블록을 그대로 복사할 수 있습니다.
2. 복사해서 만들어진 `||input:on button pressed||` 블록에서, 버튼을 `B` 로 변경합니다.
3. 모든 `hours` 변수를 `minutes` 로 바꿉니다. `23` 값을 `||logic:if||` 조건문에서 찾아 `59` 로 바꿉니다. 이 값은 최대로 가능한 분을 의미합니다.

```blocks
let minutes = 0;
input.onButtonPressed(Button.B, () => {
    if (minutes < 59) {
        minutes += 1;
    } else {
        minutes = 0;
    }
})
```

### 24 시간, 12 시간 모드 선택하기

시간은 24 시간이나 12 시간 형식으로 보여줄 수 있습니다. 버튼을 추가해서 시간을 보여주는 형식을 선택할 수 있도록 할 것입니다. 12 시간 형식으로 출력하게 되면, 마지막에 'AM' 또는 'PM' 을 추가로 더 붙일 것입니다.

1. **입력** 카테고리에서, `||input:on button pressed||` 을 가져옵니다. 버튼을 `A+B` 로 바꿉니다.
2. `||variables:set to||` 블록을 가져와 값을 변경할 변수를 `ampm` 로 바꿉니다. `||logic:not||` 를 **논리** 카테고리에서 가져와 `0` 부분을 바꿔 넣습니다.
3. `ampm` 를 **변수** 카테고리에서 가져온 후, `||logic:not||` 블록의 오른쪽에 연결시킵니다. 이렇게 24 시간 형식과 12 시간 형식을 번갈아 바꿀 수 있습니다.

```blocks
let ampm = false;
input.onButtonPressed(Button.AB, () => {
    ampm = !(ampm);
})
```

## 시간 타이머 만들기

시계에는 3 가지 기능이 있습니다.: 시간 출력, 시간 설정, 시간 타이머. 어떤 순간부터 시작해서 흐른 시간과 분을 잴 수 있는 방법이 필요합니다. 이제 시간 타이머 기능을 코딩해보겠습니다.

1. **기본** 카테고리에서, `||basic:forever||` 을 가져옵니다.
2. **기본** 카테고리에서, `||basic:pause||` 블록을 가져와 반복 실행 구조 안에 넣습니다. 중지 시간을 `100` 에서 `60000` 으로 바꿉니다. 밀리초 단위의 시간값이기 때문에, 60 초마다 한 번씩 카운트 될 수 있도록 만들어야 합니다.
3. `||basic:pause||` 아래에, `||logic:if then else||` 블록을 붙여넣습니다. `||logic:if||` 블록의 조건식을 `||logic:0 < 0||` 로 바꿉니다.
4. 왼쪽에 있는 `0` 을 `minutes` 변수로 바꿉니다. 오른쪽에 있는 `0` 값을 `59` 로 바꿉니다.
5. `||variables:change by||` 블록을 `||logic:then||` 블록 안쪽으로 넣습니다. 값을 `minutes` 변수로 바꿉니다.
6. `||variables:set to||` 블록을 가져온 후, `||logic:else||` 블록 안에 넣습니다. 다시, `minutes` 변수로 값을 바꿉니다.

```blocks
let minutes = 0;
basic.forever(() => {
    basic.pause(60000)
    if (minutes < 59) {
        minutes += 1;
    } else {
        minutes = 0;
    }
})
```

**계속 코딩하기...**

1. 자, 이제 다른 `||logic:if then else||` 를 가져온 후, `||variables:set to||` 아래에 붙입니다. 첫 번째 `||logic:else||` 에 넣으면 됩니다.
2. 두 번째 `||logic:if||` 안에, `||logic:0 < 0||` 조건식을 넣습니다. 왼쪽의 `0` 값을 `hours` 변수로 바꿉니다. 값 `0` 을 `23` 으로 바꿉니다. 23 까지 카운트를 하고, 그 다음에는 다시 0 (자정) 으로 바뀝니다.
3. `||variables:change by||` 블록을 두번째 `||logic:then||` 블록의 안쪽으로 넣습니다. 값을 `hours` 변수로 바꿉니다.
4. `||variables:set to||` 블록을 가져온 후, 두 번째 `||logic:else||` 블록 안에 넣습니다. 그리고 다시, `hours` 변수로 값을 바꿉니다. 자, 이제 시간 타이머를 동작시킬 준비가 되었습니다.

```blocks
let minutes = 0
let hours = 0
basic.forever(() => {
    basic.pause(60000)
    if (minutes < 59) {
        minutes += 1
    } else {
        minutes = 0
        if (hours < 23) {
            hours += 1
        } else {
            hours = 0
        }
    }
})
```

## 흔들어 시간을 출력해보세요!

이제 이전에 만든 디스플레이 출력 코드로 돌아갈 것입니다. 그리고 실제 시간을 출력하도록 만들것입니다! 이번 단계는 여러 가지를 바쁘게 만들겠지만, 잘 만들 수 있습니다.

첫 번째로, 12 시간 형식을 사용하려는 경우에 시간을 조정하는 코드를 만들어야 합니다.

1. 이전에 만들었던 `||input:on shake||` 블록을 찾습니다. 그 안에 들어있는 블록들을 끄집어낸 후 휴지통으로 버립니다. 다시 만들 것입니다.
2. `||variables:set to||` 를 가져와 `||input:on shake||` 안에 넣습니다. 변수의 이름을 `adjust` 로 바꿉니다. 오른쪽에 있는 `0` 값을 `hours` 변수로 바꿉니다.
3. `||logic:if then||` 블록을 가져온 후, `||variables:set to||` 아래에 붙입니다. 조건식을 `ampm` 변수로 바꿉니다.
4. `||logic:if then else||` 블록을 가져온 후, `||logic:then||` 부분에 넣습니다. `||logic:if then||` 블록의 첫 번째 부분에 있습니다. 조건식을 `||logic:0 < 0||` 로 바꿉니다. 왼쪽에 있는 `0` 값을 `hours` 변수로 바꿉니다. 오른쪽에 있는 `0` 값을 `12` 로 바꿉니다. `<` 를 `>` 로 바꿉니다.
5. 새로운 `||variables:set to||` 블록을 가져온 후, `||logic:then||` 블록 안에 넣습니다. `||logic:if then else||` 의 두 번째 블록에 넣으면 됩니다. 변수의 이름을 `adjust` 로 바꿉니다. **계산** 카테고리에서 `||math:0 - 0||` 블록을 가져온 후, 값 `0` 부분에 바꾸어 넣습니다. `||variables:set to||` 에 있는 부분에 넣으면 됩니다. 왼쪽에 있는 `0` 을 `hours` 변수로 바꾸고, 오른쪽에 있는 `0` 값을 `12` 로 바꿉니다.
6. 새로운 `||logic:if then||` 블록을 가져온 후, `||logic:else||` 블록 안에 넣습니다. 조건식을 `||logic:0 = 0||` 로 바꿉니다. `hours` 변수를, `0` 의 왼쪽에 넣습니다.
7. 마지막 `||logic:if then||` 블록의 안쪽에 `||variables:set to||` 블록을 넣습니다. 변수를 `adjust` 로 바꾸고, 그 값을 `12` 로 바꿉니다.

```blocks
let hours = 0;
let adjust = 0;
let ampm = false;
input.onGesture(Gesture.Shake, () => {
    adjust = hours;
    if (ampm) {
        if (hours > 12) {
            adjust = hours - 12
        } else {
            if (hours == 0) {
                adjust = 12
            }
        }
    }
})
```

**계속 코딩하기...**

이제, 시계에서 출력되는 시간표시 형태로 만들기 위해서 시간과 분을 연결시켜야 합니다.

1. `||input:on shake||` 블록의 마지막에, `||variables:set to||` 를 집어넣습니다. 변수의 이름을 `time` 으로 바꿉니다. 이 변수를 `||text:join||` 에 연결시킵니다. **문자열** 카테고리 안에서 찾을 수 있습니다.
2. 이 `||variables:set to||` 블록을 오른쪽 클릭한 후, **복사** 눌러 3 개를 더 만듭니다. 복사한 것들까지 포함해서 4개의 블록들을 순서대로 쌓아 붙입니다.
3. 첫 번째 `||variables:set to||` 블록에서, 아래 쪽에 있는 `""` (`||text:join||` 에 있는) 값을 `adjust` 변수로 바꿉니다.
4. 두 번째 복사 블록에서, 위 쪽에 있는 `""` (`||text:join||` 에 있는) 값을 `time` 변수로 바꿉니다. `||text:join||` 블록의 아래 쪽에 있는 문자열을 `":"` 로 바꿉니다.
5. 세 번째 복사 블록에서, 위 쪽에 있는 `""` (`||text:join||` 에 있는) 값을 `time` 변수로 바꿉니다. `||text:join||` 부분에 있는 아래 쪽 문자열을 **계산** 블록에 있는 나누기로 바꿉니다. 왼쪽의 값 `0` 을 `minutes` 변수로 바꾸고, 오른쪽의 값 `0` 을 `10` 로 바꿉니다.
6. 네 번째 복사 블록에서, 위 쪽에 있는 `""` (`||text:join||` 에 있는) 값을 `time` 변수로 바꿉니다. `||text:join||` 부분에 있는 아래 쪽 문자열을 `||Math:remainder of||` 블록으로 바꿉니다. **계산** 카테고리에서 찾을 수 있습니다. 왼쪽의 값 `0` 을 `minutes` 변수로 바꾸고, 오른쪽의 값 `0` 을 `10` 로 바꿉니다.

```blocks
let minutes = 0;
let hours = 0;
let adjust = 0;
let time = "";
let ampm = false;
input.onGesture(Gesture.Shake, () => {
    adjust = hours;
    if (ampm) {
        if (hours > 12) {
            adjust = hours - 12;
        } else {
            if (hours == 0) {
                adjust = 12;
            }
        }
    }
    time = "" + adjust;
    time = time + ":";
    time = time + minutes / 10;
    time = time + minutes % 10;
})
```

**계속 코딩하기...**

자, 이제 거의 완성되어가고 있습니다. 이제는 12 시간 형식일 때, 상황에 따라 'AM' 또는 'PM' 를 붙여야 합니다. 그렇게 완성 시킨 후에는 시간 문자열을 완성할 수 있습니다.

1. `||logic:if then||` 블록을 `||input:on shake||` 마지막에 붙여 넣습니다. 조건식 `참(true)` 을 `ampm` 변수로 바꿉니다.
2. `||logic:if then else||`블록을 `||logic:if then||` 블록 안에 넣습니다. 조건식으로 `||logic:0 < 0||` 를 사용합니다. 왼쪽의 `0` 값을 `hours` 변수로 바꿉니다. 값 `0` 을 `11` 로 바꿉니다. `<` 를 `>` 로 바꿉니다.
3. `||variables:set to||`블록을 `||logic:then||` 에 넣습니다. 값을 `time` 변수로 바꾸고, `||text:join||` 블록에 붙입니다. `||text:join||` 블록의 첫 번째 부분을 `time` 변수로 바꾸고, 두 번째 부분을 `"PM"` 으로 바꿉니다.
4. 똑같은 방법으로 마지막 단계를 진행하는데, `||variables:set to||` 블록을 `||logic:else||` 블록의 아래에 붙입니다. 하지만, 이번에는 `||text:join||` 블록의 두 번째 부분을 `"AM"` 으로 바꿉니다.
5. 마지막으로, `||input:on shake||` 안쪽의 가장 마지막에, `||basic:show  string||` 을 붙여넣습니다. **기본** 카테고리에서 찾을 수 있습니다. `"Hello!"` 문자열을 `time` 변수로 바꿉니다.

```blocks
let minutes = 0;
let hours = 0;
let adjust = 0;
let time = "";
let ampm = false;
input.onGesture(Gesture.Shake, () => {
    adjust = hours;
    if (ampm) {
        if (hours > 12) {
            adjust = hours - 12
        } else {
            if (hours == 0) {
                adjust = 12
            }
        }
    }
    time = "" + adjust;
    time = time + ":"
    time = time + minutes / 10
    time = time + minutes % 10
    if (ampm) {
        if (hours > 11) {
            time = time + "PM"
        } else {
            time = time + "AM"
        }
    }
    basic.showString(time)
})
```

## 이제 모두 완성되었습니다!

와 정말 멋집니다! 여러분의 손목 시계를 위해 필요한 프로그램코드를 모두 만들었고, 테스트 할 준비가 되었습니다. `|Download|` 를 눌러 @boardname@ 에 업로드해보세요. 흔들면, 현재 시간이 나타나게 될 것입니다.

그리고, 24 시간 형식으로 `0` 시부터 `23` 시까지 표시된 다음에는 다시 `0` 시로 바뀌게 될 것입니다. **A+B** 버튼을 누르면 12 시간 표시 형식으로 바뀝니다.: `12` 시부터 `12` 시까지로만 `1` 시부터 `11` 11시까지 시간이 바뀔 것입니다. 거기에 `"AM"` 이나 `"PM"` 이 마지막에 더 붙어 출력될 것입니다.

현재 시간으로 맞추려면, **A** 버튼과 **B** 버튼을 사용해 맞추면 됩니다. **A** 버튼을 한 번 누를 때마다, 1시간씩 올릴 수 있습니다. **B** 버튼을 누르면, 1분씩 올릴 수 있습니다.

이제 여러분이 만든 @boardname@ 를 이용해, 여러분들이 원하는 것들을 언제 이뤄낼 지 알려 줄 것입니다. 그 시간이 언제인지는 오로지 시간만 알고 있겠죠?