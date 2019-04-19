# 이벤트 처리기

이벤트 처리기 - 동작 과정

이벤트 처리기는 어떤 특정 이벤트와 연관되어있는 코드입니다. 예를 들어 "A 버튼을 누르면" 과 같은 이벤트들입니다. 이벤트와 이벤트 처리기를 다음과 같은 유형의 함수를 이용해 호출하는 방법으로 연결시킬 수 있습니다. "~하면 실행 <event>". 이벤트와 이벤트 처리기를 연결시키면 그 이벤트가 발생했을 때, 등록한 코드들을 실행 시키게 됩니다.

## 이벤트 처리기 등록하기

다음과 같은 이름을 가진 함수, "~하면 실행 <event>" 은 어떤 이벤트와 이벤트 처리기의 코드들을 연결시켜 동작시키는 함수들입니다. 예를 들어, 다음은 A 버튼을 누르는 이벤트가 발생했을 때의 이벤트 처리 코드를 등록하는 예시입니다. (이벤트 처리기의 코드 중 `do` 와 `end` 예약어 사이의 코드들이 실행되는 것입니다.) :

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString("hello", 150)
})
```

코드가 실행되면, A 버튼이 눌릴 때마다 "hello" 가 출력될 것입니다.

## 이벤트 처리기는 프로그램이 실행되면 계속 활성화된 상태로 남아있습니다.

어떤 이벤트에 대한 이벤트 처리를 위와 같이 등록하게 되면, 프로그램이 실행되는 동안 계속 이벤트 처리기가 활성화 되어있게 됩니다. A 버튼이 눌릴 때마다 "hello"가 출력되는 것을 멈추고 싶다면, 다음과 같은 코드를 다시 한 번 실행시켜야 합니다.:

```blocks
input.onButtonPressed(Button.A, () => {
})
```

위 코드는 A 버튼을 눌렀을 때 실행시키는 이벤트 처리기로서, A 버튼을 눌렀을 때 아무 작업도 실행하지 않도록 만드는 코드입니다.

## 각 이벤트 처리기는 한 가지 이벤트에 대해서만 유일하게 있습니다.

이전의 예시에서, 각 이벤트를 처리하기 위해서 한 가지의 이벤트 처리기만을 사용했습니다. 그렇다면 다음 코드는 어떻게 실행이 될까요?

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString("hello", 150)
})
input.onButtonPressed(Button.A, () => {
    basic.showString("goodbye", 150)
})
```

A 버튼을 누르면, "goodbye"가 출력됩니다. 따라서, "hello"와 "goodbye"가 모두 출력되도록 하고 싶다면 코드를 다음과 같이 작성해야 합니다.:

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showString("hello", 150)
    basic.showString("goodbye", 150)
})
```

## 자세히 알아보기

@boardname@ 에서 순서대로 실행시킬 작업들을 이벤트 처리기에 등록하는 더 자세한 사항은 [ @boardname@ - 반응 시스템](/device/reactive) 을 살펴보세요.

## 참고 항목

[버튼 누르면 실행](/reference/input/on-button-pressed), [핀 up 되면 실행](/reference/input/on-pin-pressed), [흔들면 실행](/reference/input/on-gesture)