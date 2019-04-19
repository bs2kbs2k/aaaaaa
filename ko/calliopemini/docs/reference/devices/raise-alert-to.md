# 경고 동작 명령 전송

원격으로 연결된 리모트 장치에 경고 동작을 실행할 수 있습니다.

### ~hint

The functions in the `devices` namespace allow the @boardname@ to communicate with a separate (remote) device, such as a smartphone, over Bluetooth (Smart). The set of supported events will depend on the remote device and the @boardname@ apps available for the remote device.

### ~

```sig
export function raiseAlertTo(event: string)
```

### 매개 변수

* 이벤트(event). 실행시키려는 이벤트.

### 예시

연결된 장치에서 팝업 표시 실행

```blocks
devices.raiseAlertTo("display toast")
```

연결된 장치에서 진동 경보 실행

```blocks
devices.raiseAlertTo("vibrate")
```

연결된 장치에서 사운드 재생 실행

```blocks
devices.raiseAlertTo("play sound")
```

연결된 장치에서 벨 소리 재생 실행

```blocks
devices.raiseAlertTo("play ringtone")
```

연결된 장치에서 내 스마트폰 찾기 실행

```blocks
devices.raiseAlertTo("find my phone")
```

연결된 장치에서 벨소리 경보 실행

```blocks
devices.raiseAlertTo("ring alarm")
```

### 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [카메라 동작 명령 전송](/reference/devices/tell-camera-to)

```package
장치제어
```