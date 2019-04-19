# 리모트 동작 명령 전송

`리모트 동작 명령 전송` 기능을 이용하면, 원격으로 연결된 리모트 장치의 미디어 제어 기능에 접근할 수 있습니다.

### ~hint

The functions in the `devices` namespace allow the @boardname@ to communicate with a separate (remote) device, such as a smartphone, over Bluetooth (Smart). The set of supported events will depend on the remote device and the @boardname@ apps available for the remote device.

### ~

```sig
devices.tellRemoteControlTo(event: string)
```

### 매개 변수

* 이벤트(event). 실행시키려는 이벤트.

### 이벤트 값

* 재생
* 정지
* 일시 중지
* 앞으로
* 되감기
* 볼륨 높임
* 볼륨 낮춤
* 이전 트랙
* 다음 트랙

### 예시

연결된 장치에서 재생 실행

```blocks
devices.tellRemoteControlTo("play")
```

연결된 장치에서 정지 실행

```blocks
devices.tellRemoteControlTo("stop")
```

연결된 장치에서 다음 트랙 실행

```blocks
devices.tellRemoteControlTo("next track")
```

연결된 장치에서 이전 트랙 실행

```blocks
devices.tellRemoteControlTo("previous track")
```

연결된 장치에서 앞으로 실행

```blocks
devices.tellRemoteControlTo("forward")
```

연결된 장치에서 되감기 실행

```blocks
devices.tellRemoteControlTo("rewind")
```

연결된 장치에서 볼륨 높임 실행

```blocks
devices.tellRemoteControlTo("volume up")
```

연결된 장치에서 볼륨 낮춤 실행

```blocks
devices.tellRemoteControlTo("volume down")
```

### 참고 항목

[카메라 동작 명령 전송](/reference/devices/tell-camera-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to)

```package
장치제어
```