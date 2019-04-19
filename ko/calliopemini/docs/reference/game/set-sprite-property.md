# 스프라이트 속성 설정

Make a [sprite](/reference/game/create-sprite) store the kind of [number](/reference/types/number) you say.

```sig
let item: game.LedSprite = null;
item.set(LedSpriteProperty.X, 0);
```

### 매개 변수

* **sprite**. 속성 값을 변경하려는 스프라이트.
* 원하는 값 [(정수).](/reference/types/number) 설정하려는 스프라이트 속성 값. 다음과 같은 속성 값을 설정할 수 있습니다. 
    * `x좌표`. 아래쪽 방향으로의 위치 (`0`-`4`)
    * `y좌표`. 오른쪽 방향으로의 위치 (`0`-`4`)
    * `이동방향 각도`. 스프라이트가 바라보고 있는 이동방향의 각도 ([스프라이트 회전](/reference/game/turn) 에서 사용하는 각도)
    * `밝기`. LED 스프라이트의 밝기 ([LED 스크린 밝기](/reference/led/brightness) 에서 사용하는 밝기 값)
    * `깜박임 속도`. 스프라이트를 깜박이는 속도를 나타내는 값 (값이 크면, 스프라이트가 더 빠르게 깜박입니다.)

### 예시

다음 프로그램은 스크린의 왼쪽에 스프라이트를 생성한 후, 2 초 (2000 밀리초) 후, 스크린의 오른쪽 끝 위치로 이동시킵니다.

```blocks
let ball = game.createSprite(0, 2);
basic.pause(2000);
ball.set(LedSpriteProperty.X, 4);
```

### 참고 항목

[turn](/reference/game/turn), [brightness](/reference/led/brightness), [change sprite property](/reference/game/change-sprite-property), [get sprite property](/reference/game/get-sprite-property)