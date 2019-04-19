# 카메라 동작 명령 전송

`카메라 동작 명령 전송` 기능을 이용하면, 원격으로 연결된 리모트 장치의 사진/동영상 촬영 기능에 접근할 수 있습니다.

### ~hint

The functions in the `devices` namespace allow the @boardname@ to communicate with a separate (remote) device, such as a smartphone, over Bluetooth (Smart). The set of supported events will depend on the remote device and the @boardname@ apps available for the remote device.

### ~

```sig
devices.tellCameraTo()
```

### 매개 변수

* 이벤트(event). 실행시키려는 이벤트.

### 예시

연결된 장치에서 사진 찍기 실행

```blocks
devices.tellCameraTo("take photo")
```

연결된 장치에서 동영상 녹화 시작 실행

```blocks
devices.tellCameraTo("start video capture")
```

연결된 장치에서 동영상 녹화 중단 실행

```blocks
devices.tellCameraTo("stop video capture")
```

연결된 장치에서 앞-뒤 카메라 전환 실행

```blocks
devices.tellCameraTo("toggle front-rear")
```

연결된 장치에서 사진 촬영 모드 실행

```blocks
devices.tellCameraTo("launch photo mode")
```

연결된 장치에서 동영상 촬영 모드 실행

```blocks
devices.tellCameraTo("launch video mode")
```

연결된 장치에서 사진 촬영 모드 중단

```blocks
devices.tellCameraTo("stop photo mode")
```

연결된 장치에서 동영상 촬영 모드 중단

```blocks
devices.tellCameraTo("stop video mode")
```

### 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to)

```package
장치제어
```