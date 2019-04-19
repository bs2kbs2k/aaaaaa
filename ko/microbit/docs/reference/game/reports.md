# 스프라이트 속성 읽기

LED 스크린에 있는 스프라이트의 x좌표, y좌표, 이동방향 각도, 밝기 속성을 읽어옵니다.

LED 스크린에 있는 스프라이트의 x 좌표를 확인합니다.

```sig
export function x(_this: micro_bitSprites.LedSprite) : number
```

LED 스크린에 있는 스프라이트의 y 좌표를 확인합니다.

```sig
export function y(_this: micro_bitSprites.LedSprite) : number
```

LED 스크린에 있는 스프라이트의 밝기를 확인합니다.

```sig
export function brightness(_this: micro_bitSprites.LedSprite) : number
```

LED 스크린에 있는 스프라이트의 이동방향 각도를 확인합니다.

```sig
export function direction(_this: micro_bitSprites.LedSprite) : number
```