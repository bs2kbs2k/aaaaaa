# 말하는 기계 블록 프로그래밍 도전하기

말하는 기계 튜토리얼에 대한 코딩 도전하기

## 시작하기 전에

[말하는 기계](/lessons/answering-machine/activity) 코딩 활동을 완료하면, 다음과 같은 코드가 될 것입니다.:

```blocks
basic.showString("ASK ME A QUESTION")
```

## 도전하기 1

이제, 누군가 물어본 질문에 대한 답변을 @boardname@ 를 이용해서 yes 또는 no 로 답하도록 해야합니다. `YES` 는 `A` 버튼을 눌렀을 때 출력하도록 해야합니다. `A` 버튼을 위한 조건을 추가하고, 그 안에 `YES` 문자열 출력을 넣습니다.

```blocks
basic.showString("ASK ME A QUESTION")
input.onButtonPressed(Button.A, () => {
    basic.showString("Yes")
})
```

* 코드를 업로드하고 `실행시켜`, 예상한 것처럼 동작하는지 확인해보세요.

## 도전하기 2

NO 를 @boardname@ 에서 출력하도록 하려면 어떻게 해야할까요? `NO` 는 `B` 버튼을 눌렀을 때 출력하도록 합니다. `B` 버튼을 위한 조건을 추가하고, 그 안에 `NO` 문자열 출력을 넣습니다.

```blocks
basic.showString("ASK ME A QUESTION")
input.onButtonPressed(Button.A, () => {
    basic.showString("Yes")
})
input.onButtonPressed(Button.B, () => {
    basic.showString("NO")
})

```

* 코드를 업로드하고 `실행시켜`, 예상한 것처럼 동작하는지 확인해보세요.

## 도전하기 3

어떤 질문을 받았을 때 여러분들은 YEO 나 NO 로만 대답을 하나요? `흔들면 실행` 을 추가해서, 흔들었을 때 `MAYBE` 를 출력하도록 만들어보세요.