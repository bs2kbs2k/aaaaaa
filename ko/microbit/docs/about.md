![](/static/mb/device/pano.jpg)

# About

## @description 마이크로비트를 위한 블록 / 자바스크립트 코드 편집기, 마이크로비트는 손 안에 들어가는 크기의 조그만 컴퓨터로서 5*5 로 배치된 LED 디스플레이와 각종 센서들과 블루투스 기능을 모두 가지고 있습니다.

[BBC 마이크로비트](https://microbit.org) 는 [손바닥 크기의 컴퓨터](/device) 로서 5*5 로 배치된 25개의 LED, 무선 블루투스, 각종 센서들을 모두 갖추고 있고, 누구나 쉽게 프로그래밍 할 수 있습니다. BBC 마이크로비트는 많은 [협력사](https://www.microbit.co.uk/partners)들에 의해 함께 힘을 모아 만들어졌습니다.

마이크로비트는 쉽고 재미있게 프로그래밍 기초를 배울 수 있게 설계 되었으며, 다양한 것들을 해볼 수 있습니다. - 스위치 켜기, 여러 가지 재미있는 작품 만들기 - 웨어러블 장치 만들기, 개조하기. 아두이노와 비슷하게, 마이크로비트에도 센서, 디스플레이 등의 여러 가지 다른 장치들을 연결시킬 수 있습니다.

* [관련 문서 읽기](/docs)

## [Hardware: The Device](/device)

BBC 마이크로비트에는 각종 센서, 무선통신, 기타 기능들을 수행할 수 있는 부품들이 모두 내장되어있습니다. [하드웨어 구성](/device) 을 통해 마이크로비트로 가능한 기능들에 대해서 살펴보세요!

## ~ hint

**마이크로비트 구입처를 찾고 계신가요?** [판매처 리스트](https://microbit.org/resellers)를 살펴보세요.

## ~

## 프로그래밍 환경 : [블록](/blocks), [자바스크립트](/javascript)

웹브라우저에서 [블록 언어](/blocks) 또는 [자바스크립트 언어](/javascript) 를 사용해 프로그램을 작성할 수 있으며, [마이크로비트 API](/reference) 를 통해 작성한 프로그램을 업로드 할 수 있습니다.:

```block
input.onButtonPressed(Button.A, () => {
    basic.showString("Hi!");
})
```

```typescript
input.onButtonPressed(Button.A, () => {
    basic.showString("Hi!");
})
```

코드 편집기는 [대부분의 최신 웹브라우저](/browsers)에서 동작하며, 코드 편집기가 한 번 실행되면 인터넷 연결이 되지 않는 [오프라인](/offline) 상태에서도 동작하게 됩니다.

## [컴파일, 프로그램 업로드: 만든 프로그램을 마이크로비트에 업로드!](/device/usb)

프로그램 코드가 완성되면, USB 케이블을 이용해 마이크로비트와 컴퓨터를 연결시킵니다. 마이크로비트를 컴퓨터에 연결시키면 외부 저장 장치처럼 나타나게 됩니다.(MICROBIT 로 나타납니다.)

[블록 편집기](/blocks), [자바스크립트 편집기](/javascript) 로부터, ARM 기계어 코드(ARM thumb machine code)로 컴파일되는 과정은 웹브라우저에서 진행됩니다. ARM 2진 프로그램(ARM binary program)이 파일로 만들어집니다. 그 파일을 마이크로비트(MICROBIT) 드라이브에 복사해 넣으면, 마이크로비트에 저장되어있는 프로그램이 새로운 프로그램으로 바뀌게 됩니다.

## 시뮬레이터: 코드를 테스트 해 보세요.

웹브라우저 안에 보이는 마이크로비트 시뮬레이터를 통해, 작성한 프로그램코드를 실행시켜 볼 수 있습니다. 시뮬레이터에서는 LED 스크린 출력, 버튼 입력 뿐만 아니라, 자기(나침반) 센서, 가속도 센서, 디지털 입출력 I/O 핀과 같은 기능들도 테스트 해 볼 수 있습니다.

```sim
basic.forever(() => {
  basic.showString("Hi!");
})
input.onButtonPressed(Button.A, () => {
    led.stopAnimation();
    basic.showLeds(`
. . . . .
. # . # .
. . . . .
# . . . #
. # # # .`);
});
input.onButtonPressed(Button.B, () => {
    led.stopAnimation();
    basic.showLeds(`
. # . # .
# . # . #
# . . . #
. # . # .
. . # . .`);
});
```

## 배워보세요!

아주 많은 [프로젝트](/projects), [예시](/examples), [학습코드](/courses) 들을 살펴보며 시작해 볼 수 있습니다!

## C++ 프로그래밍

[C++ micro:bit runtime](http://lancaster-university.github.io/microbit-docs/) 은 [Lancaster University](http://www.lancaster.ac.uk/)에 의해 마이크로비트의 하드웨어 기능들을 사용할 수 있도록 만들어졌습니다. 여러 가지 함수들을 제공할 뿐만 아니라 다양한 보조 함수들(수/이미지/문자열을 LED 스크린에 출력하는 기능)도 제공합니다.

[micro:bit library](/reference) 는 C++ library 의 마이크로비트 버전이라고 할 수 있습니다. 작성한 코드가 ARM 기계어 코드(machine code)로 컴파일 될 때, 자바스크립트 함수 호출은 그에 대응되는 C++ 함수들로 호출됩니다.

## [명령어 실행 도구](/cli)

주로 사용하는 코드 편집기 환경에서 @homeurl@ 을 사용해 본 적이 있나요? [명령어 실행 도구](/cli)를 설치하고 사용해 보세요!

## [Packages](/packages)

[패키지](/packages) 기능을 사용해 여러분이 직접 만들거나 수정한 블록들을 배포해보세요. 깃허브(GitHub)를 통해 배포되며 C++, JavaScript, ARM thumb 으로 만들어질 수 있습니다.

## [오픈소스](/open-source)

마이크로비트를 위한 프로그램 코드들은, 깃허브(GitHub)를 통해 [오픈 소스](/open-source) 로 운영되고 있습니다. 공헌에 함께하실 모든 분들을 환영합니다!