# Magic Button Trick

## ~avatar avatar

근처에 있는 자석을 감지하는 @boardname@ 의 자기(나침반) 센서를 이용해서 매직 버튼 트릭을 만들어보세요.

## ~

여러분의 친구들을 놀라도록 만들 수 있는, 간단한 매직 트릭입니다. @boardname@ 에서 **A** **B** 버튼에 스티커를 바꿔 붙이면, 버튼이 스티커에 따라서 바뀌는 것처럼 보입니다. 아래 동영상을 통해 마술 트릭이 어떻게 보여지는지를 먼저 살펴보세요.

https://youtu.be/-9KvmPopov8

## 이 마술 트릭의 원리

이 **마술** 의 진실은 프로그램 코드에 있습니다. 이 마술 트릭은 자석을 사용합니다. 손 안에 숨겨져 있는 자석은 @boardname@ 에게 버튼 이름을 바꿀 지 말 지를 알려줍니다. @boardname@ 주위에 자석이 있으면, **A** 버튼이 **B** 버튼처럼 보이도록 하고, **B** 버튼이 **A** 버튼처럼 보여지도록 만드는 것입니다. 트릭입니다!

## 필요한 것

이 마술 트릭을 위해서는 @boardname@ 와 손 안에 숨길 수 있는 작은 자석이 필요합니다. 냉장고 문에 붙이는 자석 종류도 잘 동작합니다.

![](/static/mb/projects/magic-button-trick/magnets.jpg "Magnets")

## 단계 1: 버튼을 눌러 **A**, **B** 가 출력되도록 만들기

마술 트릭 프로그램 코드를 만들기 전에, **A** 버튼을 눌렀을 때 'A', **B** 버튼을 눌렀을 때 'B' 가 출력되도록 하는 정상적인 프로그램을 먼저 만들어야 합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString("A")
})
input.onButtonPressed(Button.B, () => {
    basic.showString("B")
})
```

## 단계 2: 자기력 측정하기

자석을 감지하기 위해 @boardname@ 의 자기(나침반) 센서를 사용하면 됩니다. 자기(나침반) 센서를 사용하면 기본적으로 지구 자기장을 감지해서 북쪽을 찾을 수 있습니다만, 근처에 있는 다른 자석도 감지할 수 있습니다. @boardname@ 근처에 있는 자석이 있는지 다음과 같은 방법으로 감지할 수 있습니다. `||input:magnetic force||` 블록을 **입력** 카테고리에서 **... 더보기** 를 눌러 찾습니다. 자석에 의해 만들어지는 자기력의 크기만 측정하면 되기 때문에, 드롭다운 선택 메뉴에서 `크기`를 사용하면 됩니다.:

```block
let force = input.magneticForce(Dimension.Strength)
```

## 단계 3: 근처에 자석이 있는지 검사하기

이제 @boardname@ 근처에 있는 자기장을 측정할 수 있게되고, 그렇게 측정한 자기력이 어떤 값보다 큰 경우에는 근처에 강한 자석이 있다고 생각할 수 있습니다.

자석을 가지고 놀아 본 경험이 있는 사람들은, 북극(N)과 남극(S)이라고 부르는 반대 '극'성이 있다는 것을 알고 있을 것입니다. @boardname@ 가 측정하는 자기장의 값은 가까이 있는 자석의 극성에 따라, 음수(-100 과 같은)나 양수(100 과 같은 )가 모두 될 수 있습니다. We just want to know if the strength is at least 100. We don't care if its negative or positive so we also use the `||math:absolute of||` block from the **Math** menu to tell our code to ignore the negative sign and just treat `-100` as if its `100`.

그래서 다음 코드에서는, 자기(나침반) 센서로 읽어들인 자기력 값의 절댓값이 `100` 을 넘는지를 검사해 그 결과를 `isSwitched` 변수에 저장합니다.

```blocks
let force = Math.abs(input.magneticForce(Dimension.Strength));
let isSwitched = force > 100
```

## 단계 4: '근처에 자석이 있는지' 를 계속 검사하도록 만듭니다.

At the moment, our code to detect a magnet being nearby will only run once. We need to put it into a `||basic:forever||` loop so that it keeps running again and again, checking for the magnet to come near to the @boardname@. We should also make sure `isSwitched` is set to `false` when our program starts.

```blocks
let force = 0;
let isSwitched = false;
basic.forever(() => {
    force = Math.abs(input.magneticForce(Dimension.Strength));
    isSwitched = force > 100
})
```

## 단계 5: 근처에 자석이 있으면 버튼 반응 바꾸기

이제 계속해서 `isSwitched` 변수에 저장된 값을 확인할 수 있기 때문에, 그 값이 `참(true)`인 경우에 근처에 자석이 있다는 것을 알 수 있습니다. 자 이제, 버튼을 눌렀을 때의 프로그램 실행을 바꾸며 매직 버튼 트릭 마술을 위한 프로그램 코드를 완성할 수 있습니다. We will add an `||logic:if then else||` block to each button's code and check if we should swap over what's displayed for each button if `isSwitched` is equal to `true`:

```blocks
let force = 0;
let isSwitched = false;
basic.forever(() => {
    force = Math.abs(input.magneticForce(Dimension.Strength));
    isSwitched = force > 100
})

input.onButtonPressed(Button.A, () => {
    if (isSwitched) {
        basic.showString("B")
    } else {
        basic.showString("A")
    }
})
input.onButtonPressed(Button.B, () => {
    if (isSwitched) {
        basic.showString("A")
    } else {
        basic.showString("B")
    }
})
```

## 단계 6: 트릭 연습하기

@boardname@ 에 프로그램을 업로드 한 후, 매직 버튼 트릭 마술을 연습해보고, 친구들에게 보여줘 보세요. 버튼 이름 스티커를 바꾼 다음에 친구들에게 버튼을 눌러보라고 해보세요. 친구들은 매직 버튼 트릭 마술을 할 수 없을 것입니다. 여러분의 손에 숨겨진 자석에 대해서 모르기 때문입니다!

Remember, that as we are using @boardname@'s compass, it will need to be [calibrated](https://support.microbit.org/support/solutions/articles/19000008874-calibrating-the-micro-bit-compass-what-does-it-mean-when-the-micro-bit-says-draw-a-circle-or-tilt) each time we flash the program or run it for the first time.

## 원작자

This project was contributed by Brian and Jasmine Norman, aka [@MicroMonstersUK](https://twitter.com/MicroMonstersUK). You can checkout their [MicroMonsters](https://www.youtube.com/channel/UCK2DviDexh_Er2QYZerZyZQ) tutorials channel on YouTube for more projects.