# 손목시계 코드 만들기

### ~avatar avatar

손목시계에 카운터 기능을 만들어봅시다. 걸음을 걷거나 팔을 움직이는 경우와 같은 모든 움직임들을 시계에 기록할 수 있습니다.

### ~

## 활동 소요시간: ~5분

## 카운트 변수 만들기

얼마나 많은 동작들을 했는지 추적하려면 변수가 필요합니다.

1. **기본** 카테고리에서 `||basic:on start||` 블록을 가져옵니다.
2. 자, 그 다음에 **변수** 카테고리에서 `변수 만들기` 를 누릅니다. 변수의 이름을 `motions` 로 바꿉니다. `||variables:set to||` 블록을 가져온 후, 드롭다운 메뉴를 이용해 변수 이름을 `motions` 으로 바꿉니다. `||basic:on start||` 안으로 변수들을 넣습니다.
3. 아직 동작들이 카운트가 되지 않았다는 것을 알고 있습니다. `||basic:show number||` 블록을 **기본** 카테고리에서 찾아, 변수 블록 다음에 넣으세요. 이제, `0` 값을 `motions` 변수로 바꿉니다. **변수** 카테고리에서 변수들을 찾을 수 있습니다.

```blocks
let motions = 0;
motions = 0;
basic.showNumber(motions);
```

## 움직임 카운트하기

자, 이제 모든 움직임을 카운트하고 보여줘 봅시다.

1. `||input:on shake||` 블록을 **입력** 카테고리에서 찾아서, 편집화면으로 끌고 옵니다.
2. 움직임 횟수를 카운트 하기위해서, `||variables:change by||` 블록을 가져와 `||input:on shake||` 안에 집어넣습니다. `item` 변수를 `motions` 로 바꿉니다.
3. 다른 `||basic:show number||` 블록을 `||input:on shake||` 블록의 안쪽에 붙여 넣어보세요. `motions` 를 **변수** 카테고리에서 찾아, `0` 대신 집어넣습니다.

```blocks
let motions = 0;
input.onGesture(Gesture.Shake, () => {
    motions += 1;
    basic.showNumber(motions);
})
```

## 리셋!

0 부터 재시작시키고 싶은 경우, 동작 카운트를 초기화해야합니다. 두 버튼 중 하나로 그 작업을 수행하도록 해봅시다.

1. **입력** 카테고리를 눌러 `||input:on button pressed||` 을 가져옵니다. `||variables:set to||` 블록을 안에 넣으세요. 변수 이름을 `motions` 으로 바꿉니다.
2. 다른 `||basic:show number||` 블록을 더 추가하고, `0` 을 `motions` 변수로 바꿔보세요.

```blocks
let motions = 0;
input.onButtonPressed(Button.A, () => {
    motions = 0;
    basic.showNumber(motions);
})
```

## 완성되었습니다!

예! 이제 움직임 횟수를 카운트 해보세요. 이제 `|Download|` 를 눌러 프로그램 코드를 @boardname@ 에 업로드하세요. 이리 저리 걸어보고, 팔을 움직여보고, 카운트 횟수가 올라가는지 손목시계를 살펴보세요! 다시 처음부터 카운트를 시작하려면, **A** 버튼을 누르세요.

## 더 많은 손목시계 코딩 프로젝트

더 큰 도전을 해보고 싶지 않은가요? 카운트다운 손목시계나, 실제 디지털 시계를 만들어보는 것은 어떤가요? @boardname@ 손목시계 코딩 프로젝트들을 더 살펴보세요.:

* [카운트다운 타이머 만들기](/projects/watch/timer)
* [디지털 손목시계 만들기](/projects/watch/digital-watch)