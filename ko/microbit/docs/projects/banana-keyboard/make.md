# 만들기

## 준비물

* @boardname@, AAA 건전지 2개, 배터리 팩
* 바나나
* 오렌지
* 악어 집게 4개

## 단계

### `|단계 1|` - 접지 연결

![](/static/mb/lessons/banana-keyboard-1.png)

**첫 번째** 악어 집게의 한 쪽을 @boardname@ 의 **GND** 핀에 연결합니다.

### `|단계 2|` - 사운드 연결

![](/static/mb/lessons/banana-keyboard-2.png)

![](/static/mb/lessons/banana-keyboard-3.png)

**두 번째** 악어 집게의 한 쪽을 @boardname@ 의 **0** 번 핀에 연결합니다.

### `|단계 3|` - 헤드폰 접지 연결

![](/static/mb/lessons/banana-keyboard-4.png)

**첫 번째** 악어 집게의 다른 한 쪽을 헤드폰 연결잭의 가장 안쪽, 베이스 부분에 연결합니다.

### `|단계 4|` - 헤드폰 사운드 연결

![](/static/mb/lessons/banana-keyboard-5.png)

![](/static/mb/lessons/banana-keyboard-6.png)

**두 번째** 악어 집게의 다른 한 쪽을 헤드폰 연결잭의 가장 바깥쪽, 팁 부분에 연결합니다.

### `|단계 5|` - 과일 연결

![](/static/mb/lessons/banana-keyboard-7.png)

**세 번째**악어 집게의 한 쪽을, **첫 번째** 악어 집게의 다른 한 쪽에 연결시킵니다. **GND** 에 이미 연결되어있습니다.

### `|단계 6|` - 오렌지 접지 연결

![](/static/mb/lessons/banana-keyboard-8.png)

![](/static/mb/lessons/banana-keyboard-9.png)

**세 번째** 악어 집게의 다른 한 쪽을 오렌지에 연결합니다.

### `|단계 7|` - 다른 과일 연결

![](/static/mb/lessons/banana-keyboard-10.png)

**네 번째** 악어 집게의 한 쪽을 @boardname@ 의 **1** 번 핀에 연결합니다.

### `|단계 8|` - 바나나 연결

![](/static/mb/lessons/banana-keyboard-11.png)

**네 번째** 악어 집게의 다른 한 쪽을 바나나에 연결합니다.

### `|Step 9|` - 바나나 키보드를 완성해보세요.

![](/static/mb/lessons/banana-keyboard-12.png)

여러분의 바나나 키보드 피아노가 준비되었습니다!

### `|Step 10|` - 키보드 테스트

USB 케이블을 사용해 @boardname@ 를 컴퓨터에 연결하고 다음 코드를 실행시켜보세요.:

```blocks
input.onPinPressed(TouchPin.P1, () => {
    music.playTone(music.noteFrequency(Note.C), music.beat(BeatFraction.Quarter));
});
```

한 손으로 오렌지를 잡으세요. 다른 손으로 바나나에 손을 대면 소리가 나게 됩니다. 바나나 키보드가 완성되었습니다!

## ~button /projects/banana-keyboard/code

다음: 비트 박스

## ~