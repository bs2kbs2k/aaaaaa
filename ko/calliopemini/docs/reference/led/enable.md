# LED 스크린 사용 설정

LED 스크린 화면을 켜고 끕니다.

```sig
led.enable(false);
```

### 매개 변수

* `on` is a [boolean](/reference/types/boolean) that defines the on/off state of the screen

### 예시: 화면 끄기

다음은 `B` 버튼을 눌렀을 때, LED 스크린 화면을 끄는 예시 프로그램입니다.

```typescript
input.onButtonPressed(Button.B, () => {
    led.enable(false)
});
```

### Pins: P3, P4, P6, P7, P9, P10

이 핀들은 LED 매트릭스 디스플레이와 연결되어있습니다. 그리고, 주변 빛 센서 모드와도 연관되어있습니다. 디스플레이 출력 드라이버 기능을 중지 시키려면, DAL 함수 `led.enable(false)` 를 실행시키면 됩니다. (빛 센서 모드로 사용되면 자동적으로 비활성화 됩니다.) 이후에 다시 디스플레이 출력 드라이버 기능을 활성화 하려면, `led.enable(true)` 함수를 실행시키면 됩니다.

더 자세한 내용은 다음 링크를 살펴보세요. http://tech.microbit.org/hardware/edgeconnector_ds/

### 참고 항목

[LED 끄기](/reference/led/unplot), [LED 상태](/reference/led/point), [LED 스크린](/device/screen)