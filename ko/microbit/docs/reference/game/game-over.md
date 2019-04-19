# 게임 종료

게임을 종료하고 점수를 보여줍니다.

```sig
game.gameOver();
```

## 예시

다음은 버튼을 누르라는 메시지를 출력한 후, `A` 버튼을 눌렀을 때`YOU WIN!`, `B` 버튼을 눌렀을 때 애니메이션을 출력하고 게임을 종료하는 예시입니다.

```blocks
basic.showString("PICK A BUTTON");
input.onButtonPressed(Button.A, () => {
    basic.showString("YOU WIN!");
});
input.onButtonPressed(Button.B, () => {
    game.gameOver();
});
```

## 참고 항목

[현재 점수](/reference/game/score), [점수 추가](/reference/game/add-score), [카운트다운(ms) 시작](/reference/game/start-countdown)