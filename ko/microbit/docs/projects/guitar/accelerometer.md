# Accelerometer Beat Control

## @description @boardname@ 기타: 가속도 센서를 활용해 빠르기를 조절합니다.

## ~avatar avatar

가속도 센서를 사용해 기타로 출력되는 소리의 빠르기를 조절합니다. * 개념: * 중력 * 가속도 * X, Y, Z 좌표 체계 * 빠르기 * 박자 * 값 변환(매핑) * 그래프 출력 * 절댓값

## ~

## 활동 소요시간: 30 - 45분

*가속도 센서로 조절되는 빠르기*  
https://youtu.be/kA0HpqCWsjs

## 블록

```cards
input.acceleration(Dimension.Y)
music.setTempo(120)
pins.map(0, 0, 1023,60, 320)
Math.abs(1)            
```

## 가속도 센서, 중력, 기울임!

@boardname@ 에는 **가속도 센서** 가 장착되어있기 때문에 보드에 가해지는 힘을 측정할 수 있습니다. 지구에서는, 모든 물체들이 **중력**에 의해 땅으로 끌어당겨집니다!

https://youtu.be/0SULoTKmkhI

@boardname@ 가 테이블 위에 평평하게 놓여있고, 앞면이 하늘로 방향으로 향하고 있다면, 중력의 힘이 @boardname@ 의 **Z** 축 방향으로 가해지게 됩니다.

![@boardname@ x, y, z 축 이미지](/static/mb/projects/guitar/accelleration_axis.png)

보드를 앞-뒤 방향으로 기울이면, 중력에 의해서 받는 힘이 보드의 **Y**축 방향으로도 나타나게 될 것입니다. -- 이것이 보드의 기울임을 감지하는 원리입니다!!! **Y** 축 방향의 힘이 커진다는 것은, @boardname@ 가 점점 더 세워지고 있다는 것을 의미하게 되는 것입니다!

## 다른 축 방향으로의 가속도 측정하기 (X, Y, Z 축)

가속도 센서값 블록은 밀리g(**milli-g**) 단위로 대략적으로 측정되며, 밀리g 단위는 일반적인 중력가속도 값 **g** 의 1/1000 을 의미합니다. 그리고 중력가속도라는 것은 중력에 의해서 속도가 빨라지는 속도 변화의 정도를 의미합니다.

## 단계 1: 가속도를 그래프로 출력하기

```blocks
basic.forever(() => {
    led.plotBarGraph(input.acceleration(Dimension.Y), 1023)
})
```

Y 축 방향의 가속도 변화를 감지하고, 그 값을 LED 그래프로 출력해주는 **코드**를 만듭니다.

**다운로드** 를 눌러, 프로그램 코드를 @boardname@ 에 업로드 합니다.

**LED 그래프로 1 부터 5 까지 크기의 그래프가 정상적으로 그려지는지 테스트해봅니다.**

## 추가 활동

**X** 축과 **Z** 축 방향으로도 LED 그래프를 출력해보세요. 그 차이를 잘 설명할 수 있을까요?

## ~hint

## 값 변환(매핑)

**어떤 범위에서 측정된 값을 다른 범위의 값으로 비율에 맞춰 변환시키는 것은 자주 있는 일입니다. - 예를 들어 온도와 같은 경우가 그렇습니다.**  
![화씨 온도를 섭씨 온도로 변환하기](/static/mb/projects/guitar/map_analogy.png "Fahrenheit to Celsius")

## ~

## 단계 2: 가속도를 박자 값으로 변환(매핑) 하기

**@boardname@ 에 장치된 센서들로 측정할 수 있는 물리량들은 0 부터 1023 까지의 값으로 변환되어 출력됩니다. *[값 변환(map)](/reference/pins/map)* 블록을 사용하면, 그렇게 측정한 센서값 값을 다른 범위의 비율에 맞춘 값으로 변환시킬 수 있습니다.**

```blocks
basic.forever(() => {
        music.setTempo(pins.map(Math.abs(input.acceleration(Dimension.Y)),
            0, 1023,
            60, 320))
         music.playTone(Note.C, music.beat(BeatFraction.Quarter));
})
```

**코드** 를 작성합니다. Y 축 방향의 가속도 값을 *변환* 시켜 *빠르기* 값으로 바꿔주는 코드를 작성합니다.

**다운로드** 를 눌러, 프로그램 코드를 @boardname@ 기타에 업로드 합니다.

**빠르기를 느리게/빠르게 만들 수 있는 움직임을 테스트 해봅니다.**

## 단계 3: 빛 센서 음 조절 코드와 함께 결합시킵니다.

**모두 함께 결합시키기!**

```blocks
basic.forever(() => {
        music.setTempo(pins.map(Math.abs(input.acceleration(Dimension.Y)),
            0, 1023,
            60, 320))
        music.playTone(
            input.lightLevel() * 25,
            music.beat(BeatFraction.Quarter)
        );
})
```

**이전 활동을 통해서 만든 빛 센서 값 이용 음 출력 코드에 위 코드를 결합시킵니다.**

**다운로드** 를 눌러, 프로그램 코드를 @boardname@ 기타에 업로드 합니다.

## 이제, 빛 센서와 가속도 센서를 통해 출력되는 소리의 음과 빠르기를 테스트하면서 필요한 값들을 조절해 보세요!

## ~button /projects/guitar/pinpress

다음 활동: 핀 연결 스위치

## ~