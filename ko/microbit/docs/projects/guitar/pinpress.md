# Pin Press Switch

## @description @boardname@ 기타: 기타 소리 출력을 on/off 시키기 위해 핀 연결을 사용합니다.

## ~avatar avatar

기타 소리를 on/off 시키기 위해 핀 연결 스위치를 사용합니다.

* 개념: 
    * 회로
    * 전기 도선
    * 변수/전역-변수
    * 조건/선택 실행: **`만약(if)`**, **`아니면(else)`**
    * 불 값: **`참(True)`/`거짓(False)`**

## ~

## 활동 소요시간: 약 45분

## 핀 연결, 스위치 만들기 준비물:

악어 집게 2~3개

## 블록

```cards
let on = false
on;
if (on) { } else {}
input.onPinPressed(TouchPin.P1, () => {})
```

## ~hint

## 회로 & 스위치

* **회로** 를 연결시켜 완성시키기 위해서는 전기 공급을 위한 전원 (배터리), 저항 (LED 등과 같은 저항) & 전기 도체 (금속, 물, 손) 가 필요합니다.
* **스위치** 는 회로를 닫아(연결해 완성시킴), 전원으로부터 공급되는 전기를 흐르게 하거나 반대로 끊는 역할을 합니다.

**금속 호일이나 전기 도선들은 전기를 흘릴 수 있는 매우 좋은 전기 도체입니다.**

**이 활동에서는 여러분의 몸을 전기 도체처럼 사용합니다.** **ON OFF 시키는 스위치에, 여러분의 몸이 연결되어 회로가 만들어지고 전기가 흘러 완성됩니다!**

## ~

## 단계 1: 핀 연결 테스트

```blocks
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(0)
})
input.onPinPressed(TouchPin.P1, () => {
    basic.showNumber(1)
})
input.onPinPressed(TouchPin.P2, () => {
    basic.showNumber(2)
})
```

**핀 연결 감지 코드를 작성합니다.**

**다운로드** 를 눌러, 프로그램 코드를 @boardname@ 에 업로드 합니다.

https://youtu.be/PAIU-vHqyGU

**한 손으로 @boardname@ 의 GND 핀 부분을 잡고** **다른 한 손으로는 0, 1, 2 번 핀들을 잡아보며 테스트 합니다.**

## ~hint

**각 핀을 통해 흘러나오는 전기는, 여러분의 손을 통해 `GND` 핀으로 흘러 들어가게 되고, @boardname@ 는 그렇게 연결되어 흘러 들어오는 전기 신호를 감지할 수 있게 됩니다!**

## ~

## 단계 2: 기타에 전기가 흐를 수 있는 금속 호일 설치하기

https://youtu.be/NX0ECcpXFes **기타 소리를 출력하는 동안 터치하기 쉽도록, 금속 호일을 기타의 몸체에 붙입니다.**

**금속 호일과 `GND` 핀을 악어 집게를 이용해 연결시킵니다.**

https://youtu.be/YkymZGNmkrE **기타 목 부분에 금속 호일을 추가합니다.**

**금속 호일과 `P1` 핀을 악어 집게를 이용해 연결시킵니다.**

## 단계 3: 기타를 ON OFF 시킬 수 있는 스위치를 추가합니다.

** `on` 전역 변수를 사용하면, @boardname@ 에 스위치를 동작시키기 위한 값을 전달 해서** **ON OFF 시킬 수 있습니다.**

```blocks
let on = false
basic.forever(() => {
    if (on == true) {
        basic.showString("ON")
    } else {
        basic.showString("OFF")
    }
})
input.onPinPressed(TouchPin.P1, () => {
    if (on == true) {
        on = false
    } else {
        on = true
    }
})
```

**ON/OFF 코드를 만드세요.**

**프로그램 코드를 @boardname@ 에 업로드 합니다.**

**`P1` 핀을 눌러 ON OFF LED 메시지가 바뀌는지 테스트 해보세요.**

*최종 코드 완성하기* 해야할 작업: `on = !on;` 와 같이 이전 스위치 상태에서 반대로 바꿀 수 있고, `on = true; on = false; 와 같이 스위치 상태를 직접 바꿀 수도 있습니다.`

```blocks
let on = false
basic.forever(() => {
    if (on) {
        music.setTempo(pins.map(Math.abs(input.acceleration(Dimension.Y)),
            0, 1023,
            60, 320))
        music.playTone(
            input.lightLevel() * 25,
            music.beat(BeatFraction.Quarter)
        );
    } else {
        music.rest(music.beat())
    }
})
input.onPinPressed(TouchPin.P1, () => {
    on = !on;
})
```

## 자 이제 기타 연주를 시작해보세요!

**호일로 연결해, 핀 연결 상태를 감지하는 방식으로 기타를 ON OFF 시켜보세요.** **호일이 붙어있는 두 부분을 동시에 터치하면, 스위치 상태를 바꿀 수 있습니다.**

https://youtu.be/GYmdTFvxz80