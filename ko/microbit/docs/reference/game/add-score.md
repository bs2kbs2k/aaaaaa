# 점수 추가

게임 점수를 추가합니다.

```sig
game.addScore(1)
```

### 매개 변수

* [수(정수)](/types/number). 현재 점수에 추가할 포인트. 음수는 현재 점수에서 포인트를 빼는 것을 의미함.

### 예시

다음은 `A` 버튼을 누르는 만큼 점수를 추가하고, `B` 버튼을 누르면 현재 점수를 출력하고 점수를 재설정하는 예시 코드입니다.

```blocks
input.onButtonPressed(Button.B, () => {
    basic.showNumber(game.score())
    game.setScore(0)
})
input.onButtonPressed(Button.A, () => {
    game.addScore(1)
})
```

### 참고 항목

[현재 점수](/reference/game/score), [점수 설정](/reference/game/set-score), [카운트다운(ms) 시작](/reference/game/start-countdown)