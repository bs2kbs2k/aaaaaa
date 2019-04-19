# 스프라이트 닿기 확인 벽

어떤 스프라이트가 [LED 스크린](/device/screen) 의 벽에 닿았는지 알아냅니다.

스프라이트들이 LED 스크린의 가장자리(벽) 위치에서 겹칠 수 있습니다.

```sig
let item: game.LedSprite = null;
item.isTouchingEdge();
```

## 매개 변수

* **sprite**. 벽에 닿았는지(같은 좌표인지) 확인하려는 스프라이트.

## 리턴값

`불(참/거짓)` (true/false) 값. 스프라이트가 벽에 닿은(같은 좌표인) 경우 참(true).

## 예시

다음은 LED 스크린 가운데에 스프라이트를 만들고, 그 스프라이트가 LED 스크린의 가장자리(벽) 위치로 이동해 닿으면 `EDGY!`, 가장자리 위치가 아니면 `SAFE!` 를 출력하는 예시입니다.

```blocks
let item = game.createSprite(0, 2);
if (item.isTouchingEdge()) {
    basic.showString("EDGY!");
} else {
    basic.showString("SAFE!");
}
```

## 참고 항목

[스프라이트 생성](/reference/game/create-sprite), [스프라이트 닿기 확인 벽](/reference/game/is-touching), [스프라이트 벽에서 반대로 튕기기](/reference/game/if-on-edge-bounce)