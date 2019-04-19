# 카메라 동작 명령 전송

`카메라 동작 명령 전송` 기능을 이용하면, 원격으로 연결된 리모트 장치의 사진/동영상 촬영 기능에 접근할 수 있습니다.

## ~hint

**App required** You must use one of the [micro:bit apps](https://microbit.org/guide/mobile/) to use this functionality.

## ~

```sig
devices.tellCameraTo(MesCameraEvent.TakePhoto)
```

## 매개 변수

* 이벤트(event). 실행시키려는 이벤트.

## 예시

연결된 장치에서 사진 찍기 실행

```blocks
devices.tellCameraTo(MesCameraEvent.TakePhoto)
```

To tell the connected device to start recording a video:

```blocks
devices.tellCameraTo(MesCameraEvent.StartVideoCapture)
```

To tell the connected device to stop recording a video:

```blocks
devices.tellCameraTo(MesCameraEvent.StopVideoCapture)
```

To tell the connected device to toggle front-rear:

```blocks
devices.tellCameraTo(MesCameraEvent.ToggleFrontRear)
```

To tell the connected device to launch photo mode:

```blocks
devices.tellCameraTo(MesCameraEvent.LaunchPhotoMode)
```

To tell the connected device to launch video mode:

```blocks
devices.tellCameraTo(MesCameraEvent.LaunchVideoMode)
```

To tell the connected device to stop photo mode:

```blocks
devices.tellCameraTo(MesCameraEvent.StopPhotoMode)
```

To tell the connected device to stop video mode:

```blocks
devices.tellCameraTo(MesCameraEvent.StopVideoMode)
```

## 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [경고 동작 명령 전송](/reference/devices/raise-alert-to)

```package
devices
```