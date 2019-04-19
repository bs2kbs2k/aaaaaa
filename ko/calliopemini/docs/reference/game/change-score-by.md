# 점수 변경

원하는 만큼 점수를 추가합니다.

```sig
game.addScore(1)
```

### 매개 변수

* a [number](/reference/types/number) that means how much to add to the score. A negative number means to subtract from the score.

### 예시

다음은 간단한 게임 코드 예시입니다. `A` 버튼을 최대한 많이 누릅니다. 10 초 뒤에 점수를 출력합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    game.addScore(1)
})
game.startCountdown(10000)
```

### 참고 항목

[현재 점수](/reference/game/score), [카운트다운(ms) 시작](/reference/game/start-countdown)