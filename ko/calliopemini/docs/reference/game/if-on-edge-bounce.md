# 스프라이트 벽에서 반대로 튕기기

어떤 [스프라이트](/reference/game/create-sprite) 가 [LED 스크린](/device/screen) 의 가장자리(벽)에 닿았을 때, 반대로 튕기도록 설정해줍니다.

```sig
let item = game.createSprite(0, 2);
item.ifOnEdgeBounce();
```

### 매개 변수

* **sprite**. 벽에 닿았을 때의 움직임을 설정할 스프라이트.

### 예시

다음은 스크린 가장자리(벽)에, 90 도 방향을 바라보는 스프라이트를 만들고, 벽에 닿으면 반대 방향인 -90 도로 이동 방향을 바꾸도록(튕기도록) 만드는 예시 코드입니다. -- 정확히 반대 방향으로 튕깁니다.

```blocks
let ball = game.createSprite(4, 2);
basic.showNumber(ball.get(LedSpriteProperty.Direction));
input.onButtonPressed(Button.B, () => {
    ball.ifOnEdgeBounce();
    basic.showNumber(ball.get(LedSpriteProperty.Direction));
});
```

### 참고 항목

[create sprite](/reference/game/create-sprite), [touching](/reference/game/touching), [touching edge](/reference/game/touching-edge)