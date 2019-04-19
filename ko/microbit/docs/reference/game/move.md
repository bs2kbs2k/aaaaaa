# 스프라이트 이동

원하는 LED 개수 만큼 스프라이트를 이동시킵니다.

```sig
let item: game.LedSprite = null;
item.move(1);
```

## 매개 변수

* [수(정수)](/types/number). 스프라이트를 이동시킬 LED 개수.

## 예시

다음 프로그램에서는 가운데 위치 스프라이트를 생성합니다. 그 다음에, 만들어진 스프라이트를 오른쪽아래(남동쪽) 방향으로 이동 방향을 바꿉니다. 그 후에 스프라이트의 이동 방향으로 LED 2 칸 만큼이동시켜, 오른쪽 아래 모서리로 이동시킵니다.

```blocks
let item = game.createSprite(2, 2);
item.turn(Direction.Right, 45);
item.move(2);
```

## 참고 항목

[스프라이트 회전](/reference/game/turn), [스프라이트 생성](/reference/game/create-sprite)