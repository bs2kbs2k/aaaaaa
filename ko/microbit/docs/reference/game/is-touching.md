# 스프라이트 닿기 확인

다른 스프라이트에 닿았는지(같은 좌표에 있는지)를 알아냅니다.

어떤 스프라이트가 다른 스프라이트들과 같은 LED 위치에서 겹칠 수 있습니다.

```sig
let item: game.LedSprite = null;
item.isTouching(null);
```

## 매개 변수

* **sprite**. 확인하려는 스프라이트.
* 다른 **sprite**. 닿았는지(같은 좌표인지) 확인하려는 스프라이트.

## 리턴값

`불(참/거짓)` (true/false) 값. 두 스프라이트가 닿은(같은 좌표인) 경우 참(true).

## 예시

다음은 2 개의 `matter` 와 `antimatter` 스프라이트를 생성한 후, 두 스프라이트가 닿았는지(같은 좌표인지) 확인하는 예시입니다. 두 스프라이트가 닿으면 폭발 메시지를 출력합니다.

```blocks
let matter = game.createSprite(2, 2);
let antimatter = game.createSprite(2, 2);
if (matter.isTouching(antimatter)) {
    basic.pause(500);
    basic.clearScreen();
    basic.showString("BOOM!");
}
```

## 참고 항목

[스프라이트 생성](/reference/game/create-sprite), [스프라이트 닿기 확인](/reference/game/is-touching-edge), [스프라이트 벽에서 반대로 튕기기](/reference/game/if-on-edge-bounce)