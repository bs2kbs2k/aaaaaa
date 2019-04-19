# 게임

게임 스프라이트를 이용해서 스크린에서 점이 움직이는 형태의 게임을 만들어보세요. 점수를 저장하고, 게임 플레이를 제어할 수 있습니다.

## ~ hint

게임 엔진이 시작되면, 게임 스프라이트들을 화면에 겹쳐(렌더링 해서) 출력해주기 시작하며, 애니메이션과 함께 렌더링해 출력해주는 상태로 바뀌게 됩니다. [게임 일시 중지](/reference/game/pause) 와 [게임 재개](/reference/game/resume) 블록을 사용해, 게임 렌더링(화면 겹치기) 기능을 비활성화/활성화시킬 수 있습니다.

## ~

## 스프라이트

```cards
game.createSprite(0,0);
game.createSprite(0,0).delete();
game.createSprite(0,0).move(0);
game.createSprite(0,0).turn(Direction.Left,0);
game.createSprite(0,0).ifOnEdgeBounce();
game.createSprite(0,0).get(LedSpriteProperty.X);
game.createSprite(0,0).set(LedSpriteProperty.X, 0);
game.createSprite(0,0).change(LedSpriteProperty.X, 0);
game.createSprite(0,0).isTouching(null);
game.createSprite(0,0).isTouchingEdge();
```

## 게임 점수

```cards
game.addScore(1);
game.score();
game.setScore(0);
```

## 게임 컨트롤

```cards
game.startCountdown(10000);
game.gameOver();
game.pause();
game.resume();
```

## 참고 항목

[스프라이트 생성](/reference/game/create-sprite), [스프라이트 이동](/reference/game/move), [스프라이트 회전](/reference/game/turn), [스프라이트 벽에서 반대로 튕기기](/reference/game/if-on-edge-bounce), [스프라이트 속성 읽기](/reference/game/get), [스프라이트 속성 설정](/reference/game/set), [스프라이트 속성 변경](/reference/game/change), [스프라이트 닿기 확인](/reference/game/is-touching) [스프라이트 벽에 닿았는지 확인](/reference/game/is-touching-edge), [점수 추가](/reference/game/add-score), [현재 점수](/reference/game/score), [점수 설정](/reference/game/set-score), [카운트다운(ms) 시작](/reference/game/start-countdown), [게임 종료](/reference/game/game-over), [게임 일시 중지](/reference/game/pause), [게임 재개](/reference/game/resume)