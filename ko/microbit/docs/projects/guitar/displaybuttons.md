# Buttons, Display and Sound

## @description @boardname@ 기타: 버튼들을 사용해 LED 스크린에 출력하고 소리를 냅니다.

## ~avatar avatar

버튼 이벤트를 사용해 LED 스크린에 출력하고 소리를 출력해보세요. * **개념:** * 이벤트 * 음/박자 * 악보

## ~

## 활동 소요시간: 30 - 45분

## 준비물

@boardname@, AAA 건전지 2개, 배터리 팩

![배터리 팩 및 @boardname@](/static/mb/projects/guitar/microbit.jpg)

악어 집게 2~4개

![악어 집게](/static/mb/projects/guitar/crocclips.jpg)

해드폰

![이어버드 헤드폰](/static/mb/projects/guitar/headphones.jpg)

## 블록

```cards
    basic.showLeds(`
        . # . # .
        . . . . .
        . # # # .
        . # . # .
        . # # # .
        `);
input.onButtonPressed(Button.A, () => {});
music.playTone(Note.C, music.beat(BeatFraction.Quarter))
music.rest(music.beat(BeatFraction.Whole))
music.beat(BeatFraction.Quarter)
```

## 단계 1: 스마일리 만들기

웹브라우저에서 @homeurl@ 를 엽니다

```blocks
    basic.showLeds(`
        . # . # .
        . . . . .
        . # # # .
        . # . # .
        . # # # .
        `);
```

**기본** 카테고리에서, **LED 출력** 블록을 가져옵니다. * LED 출력 모양을 만듭니다.

![@boardname@ USB 연결](/static/mb/projects/guitar/connectmicrobit.jpg) USB 케이블을 이용해 @boardname@ 를 컴퓨터에 연결하고, **`다운로드`** 를 누르세요. 프로그램을 @boardname@ 에 업로드하기 위해 다음을 따라가세요.

## 단계 2: 스마일리 LED 버튼 이벤트를 추가합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showLeds(`
        . # . # .
        . . . . .
        . # # # .
        . # . # .
        . # # # .
        `)
})
input.onButtonPressed(Button.B, () => {
    basic.showLeds(`
        . # . # .
        . . . . .
        . . . . .
        # . . . #
        . # # # .
        `)
})
```

**입력** 카테고리에서, **'A' 버튼을 누르면 실행** 블록을 가져옵니다.

* 얼굴 모양의 LED 출력 블록을 붙여넣습니다.

* 'B' 버튼을 눌렀을 때, 다른 얼굴 모양이 나타나도록 블록을 한 개 더 만드세요.

* @boardname@ 에 프로그램 코드를 업로드 한 후, A & B 버튼을 눌러 확인해보세요.

## 단계 3: 악어 집게를 사용해 헤드폰 스피커에 연결합니다.

![0 번 핀과 GND 핀을 연결하는 악어 집게](/static/mb/projects/guitar/crocclipintoboard.jpg)

![헤드폰 잭에 연결하는 악어 집게](/static/mb/projects/guitar/jacktocrocs.jpg) (검은색) 두 번째 악어 집게를 사용해 **GND** 핀과 **헤드폰 잭의 가장 안쪽 베이스** 부분을 서로 연결합니다.

다른 악어 집게를 사용해 **P0** 핀과 **헤드폰 잭의 가장 바깥쪽 팁** 을 연결합니다.

*@boardname@ 에 배터리 팩 연결하기* https://youtu.be/zwRTmpKIaVU @boardname@ & 배터리 팩을 기타 몸체에 붙이세요.

*헤드폰 스피커에 연결하기* https://youtu.be/ewyEW_U5G9M Connect the headphones with crocodile clips

## ~hint

## @boardname@ 로 음악 소리를 출력할 수 있습니다.

**소리 출력(Hz)** 블록을 사용하면, 낮은 **C(도)** 부터 높은 **B(시)** 까지의 음을 선택해 출력할 수 있습니다.. 음계와 박자를 순서대로 기록한 악보 형태로 음악을 출력할 수 있습니다. 생일 축하 노래도 같은 방법으로 출력될 수 있습니다. C(도), C(도), D(레), C(도), F(파), E(미)

```blocks
input.onButtonPressed(Button.A, () => {
    music.playTone(Note.C, music.beat(BeatFraction.Quarter))
    music.rest(music.beat(BeatFraction.Whole))
    music.playTone(Note.C, music.beat(BeatFraction.Quarter))
    music.rest(music.beat(BeatFraction.Whole))
    music.playTone(Note.D, music.beat(BeatFraction.Quarter))
    music.rest(music.beat(BeatFraction.Whole))
    music.playTone(Note.C, music.beat(BeatFraction.Quarter))
    music.rest(music.beat(BeatFraction.Whole))
    music.rest(music.beat(BeatFraction.Whole))
    music.playTone(Note.F, music.beat(BeatFraction.Half))
    music.rest(music.beat(BeatFraction.Whole))
    music.playTone(Note.E, music.beat(BeatFraction.Whole))
})
```

## ~

## 단계 4: A & B 버튼에 소리 출력 이벤트를 추가합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showLeds(`
        . # . # .
        . . . . .
        . # # # .
        . # . # .
        . # # # .
        `)
    music.playTone(Note.A, music.beat(BeatFraction.Whole))
})
input.onButtonPressed(Button.B, () => {
    basic.showLeds(`
        . # . # .
        . . . . .
        . . . . .
        # . . . #
        . # # # .
        `)
    music.playTone(Note.G, music.beat(BeatFraction.Whole))
})
```

**소리** 카테고리에서, **소리 출력(Hz)*음 C(도)**박자 1*** 블록을 가져와 **LED 출력** 블록 아래에 붙이고, **버튼 A 누르면 실행** 안에서 실행되도록 합니다.

* 출력할 **음** 을 음계 문자(*letter*)를 이용해 바꾸어 가며, 높은 음과 낮은 음들을 사용해 실험해 보세요.
* **박자** 는 1 박자로 설정합니다.

같은 방법으로 **반복** 해서, **B 버튼** 에 대한 이벤트도 작성합니다.

**다운로드** 를 눌러, 프로그램 코드를 @boardname@ 에 업로드 합니다.

헤드폰과 전원을 연결한 후, **A & B 버튼** 이 원하는데로 동작하는지 확인해보세요.

## 축하합니다. 기본 기타를 완성했습니다!

**도전해보기:** 각 버튼을 눌렀을 때, 단순한 음악 대신 더 긴 음악 샘플이 출력되도록 만들어 보세요. * *팁*: "ABC 노래 악보" 나 "쉬운 노래 악보" 들을 노래 이름으로 검색해보세요.

## 추가 활동

* [Smiley Buttons tutorial](/projects/smiley-buttons)
* [헤드폰을 해킹해보세요.](/projects/hack-your-headphones)

## ~button /projects/guitar/lightsensor

다음 활동: 빛 센서, 출력 음 제어

## ~