# 스프라이트 회전

스프라이트의 이동 방향을, 원하는 방향과 각도로 회전시킵니다.

```sig
let item: game.LedSprite = null;
item.turn(Direction.Right, 45);
```

### 매개 변수

* **왼쪽** 또는 **오른쪽**. 스프라이트의 이동방향을 바꿀 회전 방향.
* a [number](/reference/types/number) that means how much the sprite should turn. This number is in **degrees**, so a straight left or right turn is 90 degrees.

### 예시

다음 프로그램에서는 가운데 위치 스프라이트를 생성합니다. 그 다음에, 만들어진 스프라이트를 오른쪽아래(남동쪽) 방향으로 이동 방향을 바꿉니다. 그 후에 스프라이트의 이동 방향으로 LED 2 칸 만큼이동시켜, 오른쪽 아래 모서리로 이동시킵니다.

```blocks
let item = game.createSprite(2, 2);
item.turn(Direction.Right, 45);
item.move(2);
```

### 참고 항목

[스프라이트 이동](/reference/game/move), [스프라이트 회전](/reference/game/create-sprite)