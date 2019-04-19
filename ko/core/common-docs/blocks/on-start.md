# 시작하면 실행

An event that runs when the program starts.

```blocks
let thousand = 1000
```

`시작하면 실행` 은 특별한 이벤트로서, 프로그램이 시작되면 가장 먼저 실행되는 특별한 이벤트입니다. 처음에 프로그램을 초기화 할 때 사용합니다.

## #exstart

## What about JavaScript?

Where is `on start`...?

```typescript
function onStart(){} // I don't exist
```

`on start` **only** exists in the block editor. In JavaScript, all code executes sequentially starting at the first line.

## Hey, my events moved! #eventsmoved

프로그래밍 블록들을 자바스크립트로 변환하면, `시작하면` 코드를 시작하기 전에, 모든 이벤트(버튼 누름, 흔들림, ....)가 먼저 등록됩니다.

`시작하면` 블록에 의해 잠시 멈춰지면, 모든 이벤트들이 똑같이 실행될 수 있습니다.

## #eventorder

## #examples