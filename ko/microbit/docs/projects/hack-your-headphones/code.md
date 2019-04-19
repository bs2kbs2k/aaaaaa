# 코드 만들기

## ~avatar avatar

빛의 밝기에 따라 다르게 나오는 비트 박스 전자 음악 소리를 만들어 본 적이 있나요? 프로그래밍 코드를 이용해 비트 박스를 함께 만들어보세요!

## ~

데이터를 저장해두었다가 다시 사용할 수 있도록 변수를 하나 만드세요. 그 변수의 이름을 "light" 로 바꾸어주세요. 그 다음에 입력 카테고리에 있는 `LED 스크린 빛 센서 밝기` 값을 그 변수에 저장시킵니다. `LED 스크린 빛 센서 밝기` 를 사용하면 0 (어두움) 부터 255 (가장 밝음) 범위의 값으로 측정한 주변의 밝기 값을 읽어오게 됩니다. 주변 빛의 밝기는 LED 스크린에 있는 여러 개의 LED를 통해 측정됩니다. 코드를 수정해 다음과 같이 만들어보세요.

```blocks
input.onButtonPressed(Button.A, () => {
    let light = input.lightLevel();
});
```

이제는 버튼을 눌렀을 때 음악이 나오는 코드를 만들어야 합니다. 프로그램을 실행시키고 버튼을 눌렀을 때 원하는 코드를 동작시키는 이벤트 핸들러를 등록하면 됩니다. 입력 카테고리에서 `버튼 누르면 실행` 블록을 가져와 A 버튼으로 설정합니다. 그 다음에 아무 소리도 출력하지 않도록 `지속 시간` 블록을 `1/16` 박자로 선택합니다. 코드를 수정해 다음과 같이 만들어보세요.

```blocks
input.onButtonPressed(Button.A, () => {
    music.rest(music.beat(BeatFraction.Sixteenth));
    let light = input.lightLevel();
});
```

다음으로 논리 카테고리를 눌러 `만약(if)` 블록을 가져옵니다. 이 블록을 사용하면 조건식의 결과인 참 거짓에 따라 다르게 실행할 수 있도록 만들 수 있습니다. 그 다음에 `light` 변수를 첫 번째 조건식 부분에 넣습니다. 변수 카테고리에서 "light" 블록을 찾아서 가져올 수 있습니다. 마지막으로, 그 조건식에서 비교할 값으로 25 를 입력합니다. 코드를 수정해 다음과 같이 만들어보세요. 만약 `LED 스크린 빛 센서 밝기` 가 25 보다 `작으면`, `소리 출력(Hz)` 으로 `C(도)` 음을 출력하도록 합니다. 그렇지 않으면, `소리 출력(Hz)` 으로 `A(라)` 음을 출력하도록 합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    music.rest(music.beat(BeatFraction.Sixteenth));
    let light = input.lightLevel();
    if (light < 25) {
        music.ringTone(music.noteFrequency(Note.C));
    }
    else {
        music.ringTone(music.noteFrequency(Note.A));
    }
});
```

이제 논리 카테고리를 눌러 `작다` 블록을 가져온 후, 첫 번째 `만약(if)` 블록에 집어 넣습니다. 결과 값의 참 거짓에 따라 다르게 실행될 것입니다. 이런 논리적 과정을 조건식으로 만들어 계속 구성해 나갑니다. 논리 카테고리를 누릅니다. `만약(if)` 블록의 왼쪽 위에 있는 톱니바퀴 아이콘을 눌러, 조건/선택 실행 구조를 바꾸어야 합니다. 5 개의 `else if` 와 1 개의 `else` 블록 구조를 가진 `만약(if)` 블록으로 구조를 바꿉니다. 만약 `LED 스크린 빛 센서 밝기` 가 50 보다 `작으면`, `소리 출력(Hz)` 으로 `D(레)` 음을 출력하도록 합니다. 그렇지 않고, `LED 스크린 빛 센서 밝기` 가 100 보다 `작으면`, `소리 출력(Hz)` 으로 `C(도)` 음을 출력하도록 합니다. 계속해서, `LED 스크린 빛 센서 밝기` 가 150 보다 `작으면`, `소리 출력(Hz)` 으로 `F(파)` 음을, `LED 스크린 빛 센서 밝기` 가 180 보다 `작으면`, `소리 출력(Hz)` 으로 `G(솔)` 음을 출력하도록 만듭니다. 그리고 마지막으로, 이전의 모든 경우가 아니면(거짓이면), `소리 출력(Hz)` 으로 `A(라)` 음을 출력하도록 합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    music.rest(music.beat(BeatFraction.Sixteenth));
    let light = input.lightLevel();
    if (light < 25) {
        music.ringTone(music.noteFrequency(Note.C));
    }
    else if (light < 50) {
        music.ringTone(music.noteFrequency(Note.D));
    }
    else if (light < 100) {
        music.ringTone(music.noteFrequency(Note.E));
    }
    else if (light < 150) {
        music.ringTone(music.noteFrequency(Note.F));
    }
    else if (light < 180) {
        music.ringTone(music.noteFrequency(Note.G));
    }
    else {
        music.ringTone(music.noteFrequency(Note.A));
    }
});
```

* **|download|** 를 눌러 @boardname@ 에서 실행시켜보세요.