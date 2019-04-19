# Light Sensor Tone control

## @description @boardname@ 기타: 출력되는 음을 빛 센서를 활용해 조절합니다.

## ~avatar avatar

[테러민](https://en.wikipedia.org/wiki/Theremin) 라는 전자 악기와 비슷하게, 빛 센서 값으로 소리 출력이 제어되는 기타를 만들어보세요.

* **개념:** 
     * 입력
     * 빛의 세기
     * 음/주파수
     * 비율 매핑(변환)
     * 무한 반복 실행
     * 계산 (곱셈) 을 활용한 코드값 곱셈

## ~

## 활동 소요시간: 30 - 45분

*빛 센서 이용해 음 출력하기* https://youtu.be/2cKg9pokVC4

## @boardname@ 의 LED 빛 센서

* @boardname@ 는 LED 스크린으로 들어오는 주변 빛의 세기를 측정할 수 있습니다.
* 빛 센서의 빛 값을 읽어오는 블록을 사용하면, 주변 빛의 양을 0 (*어두움*) 부터 255 (*밝음*) 범위로 알아낼 수 있습니다.
* **무한 반복 실행** 은 계속적으로 빛 센서 값을 읽어오면서, 출력되는 음을 제어하기 위해 필요합니다.

## 무한 반복 실행

무한 반복 실행 구조는 실제로 무한히 반복 실행됩니다. 무한 반복 실행 구조는 어떤 이벤트가 발생했는지를 계속 검사하거나, 코드에 포함되어있는 변수의 값을 바꾸는데 편리하게 사용될 수 있습니다.

## 블록

```cards
basic.forever(() => {})
input.lightLevel()
led.plotBarGraph(0, 255)
music.playTone(Note.C, music.beat(BeatFraction.Quarter))
```

## 단계 1: 주변 빛 세기 측정장치 만들기

```blocks
basic.forever(() => {
    led.plotBarGraph(input.lightLevel(), 255)
})
```

**블록들을 만듭니다.** * **기본** 카테고리에서 **무한 반복 실행** 블록을 가져옵니다. * **LED** 카테고리에서 **LED 그래프** 블록을 가져와 **무한 반복 실행** 블록 안에 넣습니다. * **입력** 카테고리에서 **LED 스크린 빛 센서 밝기** 블록을 가져와 **LED 그래프* 입력에 * 붙여넣습니다.**

** *LED 그래프* 의 *최댓값* 을 *255* 로 설정합니다.**

## 단계 2: LED 그래프로 더 높게 출력되도록 할 수 있는 빛 센서값을 테스트해보세요.

*LED 그래프 입력* https://youtu.be/pqU7bTcfQ_s **LED 그래프** 의 ***최댓값*** 을 바꿔가면서, LED 그래프로 그려지는 모양들이 어떻게 바뀌는지 실험해보세요.

**255 는 최댓값으로 사용할 수 있는 가장 큰 값입니다.** 255 보다 작은 값으로 테스트해보면서, LED 그래프로 출력되는 높이가 1 부터 - 5 까지 고르게 나올 수 있는 **최댓값**을 찾아보세요.

## ~hint

## 진동수/주파수

**진동수/주파수/주기** 는 1초 동안에 측정된 파형의 개수 또는 진동의 개수를 의미하며 그 단위는 헤르츠(Hz) 로 나타냅니다. 즉 1초당 몇 번? 의 의미를 가지는 단위라고 할 수 있습니다. * 건강한 보통 사람의 경우 20Hz 에서 20,000Hz 주파수 범위의 소리를 들을 수 있습니다. * @boardname@ 와 연결한 헤드폰으로는 ~50Hz - 6,000Hz 주파수 범위의 소리를 안정적으로 출력할 수 있습니다.

**261Hz** 는 C(도) 음의 소리 주파수 입니다.

```blocks
music.playTone(261, music.beat(BeatFraction.Half))
```

**소리 출력(Hz)** 블록을 사용하면 원하는 **주파수/진동수** 를 직접 입력할 수도 있습니다. **C** 라고 쓰여있는 부분을 **정수** 블록을 이용해 원하는 주파수/진동수로 바꾸어 넣으면 됩니다.

```blocks
music.playTone(261, music.beat(BeatFraction.Half))
```

## ~

## 단계 3: 계산 블록을 사용해 진동수/주파수 곱하기(옥타브 올리기)

```blocks
input.onButtonPressed(Button.A, () => {
    music.playTone(261 * 2, music.beat(BeatFraction.Half))
})
```

Create a **play tone** block using a **Math** section, **multiplication** block to set *tone*

## 다음

**Add** a **B** button block that multiplies the **261** tone by a number other than 2 to set tone

**Download the code to the @boardname@**

**Test the sound for multiples of the 261Hz *C* frequency**

## Step 4: Control the Frequency with the light input

```blocks
basic.forever(() => {
    music.playTone(input.lightLevel() * 25, music.beat(BeatFraction.Quarter))
})
```

**Create a *forever loop* containing a *play tone* block**

**Set *tone*, using *Math* multiplication block that multiplies *light level* input by 25** or experiment with multipliers larger and smaller than 25

**Test light tone control on the guitar** Cover the LEDs with your hand to vary light detected to control the tone

## Good work, this guitar is sounding good!

**Challenge:** Create a variable for the light level multiplier that you can change using buttons (optional)

## ~button /projects/guitar/accelerometer

NEXT: Accelerometer Beat control

## ~