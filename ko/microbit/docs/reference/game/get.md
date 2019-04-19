# 스프라이트 속성 읽기

[sprite](/reference/game/create-sprite) 의 원하는 속성 값을 읽어옵니다.

```sig
let item: game.LedSprite = null;
item.get(LedSpriteProperty.X);
```

## 매개 변수

* **sprite**. 속성 값을 읽어올 스프라이트.
* 원하는 값 [(정수).](/types/number) 읽어오려는 스프라이트 속성 값. 다음과 같은 속성 값을 읽어올 수 있습니다. 
    * `x좌표`. 아래쪽 방향으로의 위치 (`0`-`4`)
    * `y좌표`. 오른쪽 방향으로의 위치 (`0`-`4`)
    * `이동방향 각도`. 스프라이트가 바라보고 있는 이동방향의 각도 ([스프라이트 회전](/reference/game/turn) 에서 사용하는 각도)
    * `밝기`. LED 스프라이트의 밝기 ([LED 스크린 밝기](/reference/led/brightness) 에서 사용하는 밝기 값)
    * `깜박임 속도`. 스프라이트를 깜박이는 속도를 나타내는 값 (값이 크면, 스프라이트가 더 빠르게 깜박입니다.)

## 리턴값

[수(정수)](/types/number). 스프라이트 속성 값.

## 예시

다음은 스프라이트를 생성하고, 그 스프라이트의 밝기를 출력합니다.

```blocks
let ball = game.createSprite(0, 2);
basic.showNumber(ball.get(LedSpriteProperty.Brightness));
```

## 참고 항목

[스프라이트 회전](/reference/game/turn), [스프라이트 밝기](/reference/led/brightness), [스프라이트 속성 변경](/reference/game/change), [스프라이트 속성 설정](/reference/game/set)