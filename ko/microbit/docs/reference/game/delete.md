# delete

게임에서 스프라이트를 삭제합니다.

```sig
let item: game.LedSprite = null;
item.delete();
```

### 매개 변수

* **sprite**. 게임에서 삭제하고자하는 스프라이트.

### 예시

다음은 스프라이트를 생성하고, 스프라이트의 밝기를 출력합니다. 그 후에 스프라이트를 게임에서 삭제합니다.

```blocks
let ball = game.createSprite(0, 2);
basic.showNumber(ball.get(LedSpriteProperty.Brightness));
ball.delete();
```

### 참고 항목

[create sprite](/reference/game/create-sprite)