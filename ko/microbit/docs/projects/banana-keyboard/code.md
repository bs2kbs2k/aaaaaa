# 코드 만들기

비트 박스 전자 음악 소리를 만들어 본 적이 있나요? 프로그래밍 코드를 이용해, 바나나 비트 박스를 함께 만들어보세요!

## 바나나 키보드 코드 만들기

음계를 저장할 수 있도록 변수를 추가합니다. 변수의 이름을 `sound` 로 바꿉니다. `A(라)` 값을 그 변수에 저장시킵니다. **소리** 카테고리에서 찾을 수 있습니다.

```blocks
let sound = music.noteFrequency(Note.A);
```

핀이 연결 되었을 때 소리가 나도록 해야합니다. **1** 핀이 연결될 때마다 작업을 실행시킬 이벤트 처리기를 등록합니다. 물론 **1** 번 핀은 바나나에 연결되어있습니다. `||input:on pin pressed||` 블록을 **입력** 카테고리에서 가져옵니다.

```blocks
let sound = music.noteFrequency(Note.A);
input.onPinPressed(TouchPin.P1, () => {

})
```

이제 바나나가 연결되었을 때 음계 소리를 출력해주는 코드를 만들어보세요. **반복** 카테고리에서 `||loops:repeat||` 반복을 가져와 `||input:on pin pressed||` 블록 안에 넣습니다. **변수** 를 눌러, `||variables:change item by||` 블록을 가져와 반복 구조 안에 넣습니다. 변수의 이름을 `sound` 로 바꿉니다. 그 값을 `1` 에서 `25` 로 변경합니다. 이렇게 하면 `sound` 변수에 저장되어있는 `Middle A` 음을 `Middle A` + 25 로 값을 더해가게 됩니다. `||variables:set to||` 블록의 왼쪽에 `sound` 변수를 넣습니다. 바나나가 연결되면, `Middle A` 로 재설정되도록 합니다.

```blocks
let sound = music.noteFrequency(Note.A);

input.onPinPressed(TouchPin.P1, () => {
    for (let i = 0; i < 4; i++) {
        sound += 25;
    }
    sound = music.noteFrequency(Note.A);
});
```

마지막으로, `||music:play tone||` 블록을 `||variables:change by||` 앞에 넣습니다. `sound` 변수 블록을 가져와 `||music:play tone||` 의 음계 슬롯에 넣습니다. 박자를 `1` 에서 `1/4` 로 변경합니다.

```blocks
let sound = music.noteFrequency(Note.A);

input.onPinPressed(TouchPin.P1, () => {
    for (let i = 0; i < 4; i++) {
        music.playTone(sound, music.beat(BeatFraction.Quarter));
        sound += 25;
    }
    sound = music.noteFrequency(Note.A);
});
```

`|Download|` 를 눌러 프로그램을 업로드하고 바나나를 눌러보세요. 4 개의 음이 출력되는 것이 들리나요?

## 다른 바나나 키 추가하기

**[바나나 키보드 만들기](/projects/banana-keyboard/make)** 로 돌아가서 단계 7 과 단계 8 을 반복하되, 이번에는 **3** 번 핀에 악어 집게를 연결합니다.

`||input:on pin pressed||` 이벤트 처리기를 복사합니다. 복사해서 만들어진 `||input:on pin pressed||` 블록에서, 핀 번호를 **P2** 로 변경합니다. **P2** 핀에 대한 이벤트에서, `sound` 변수에 저장되는 값을 25 만큼씩 줄이도록 합니다. `25` 값을 `||variables:change by||` 블록에서 찾아 `-25` 로 바꿉니다. 이제, 다음과 같은 코드와 같게 될 것입니다.:

```blocks
let sound = music.noteFrequency(Note.A);

input.onPinPressed(TouchPin.P1, () => {
    for (let i = 0; i < 4; i++) {
        music.playTone(sound, music.beat(BeatFraction.Quarter));
        sound += 25;
    }
    sound = music.noteFrequency(Note.A);
});

input.onPinPressed(TouchPin.P2, () => {
    for (let i = 0; i < 4; i++) {
        music.playTone(sound, music.beat(BeatFraction.Quarter));
        sound += -25;
    }
    sound = music.noteFrequency(Note.A);
});
```

다시, `|Download|` 를 눌러 프로그램을 업로드하고, 2개의 바나나를 이용해 보세요. 과일들과 함께하는 콘서트입니다!