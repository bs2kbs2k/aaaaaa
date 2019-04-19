# 현재 점수

현재 점수를 알아냅니다.

```sig
game.score()
```

## 예시

다음은 `A` 버튼을 누를 때마다 점수를 1 점씩 추가하고, 애니메이션을 출력합니다. 그리고 500 밀리초(0.5 초) 뒤에 점수를 출력합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    game.addScore(1);
    basic.pause(500);
    basic.showNumber(game.score());
    });
```

## 참고 항목

[점수 변경](/reference/game/score), [카운트다운(ms) 시작](/reference/game/start-countdown)