# 경고 동작 명령 전송

원격으로 연결된 리모트 장치에 경고 동작을 실행할 수 있습니다.

## ~hint

**App required** You must use one of the [micro:bit apps](https://microbit.org/guide/mobile/) to use this functionality.

## ~

```sig
devices.raiseAlertTo(MesAlertEvent.Vibrate)
```

## 매개 변수

* 이벤트(event). 실행시키려는 이벤트.

## 예시

연결된 장치에서 팝업 표시 실행

```blocks
devices.raiseAlertTo(MesAlertEvent.DisplayToast)
```

연결된 장치에서 진동 경보 실행

```blocks
devices.raiseAlertTo(MesAlertEvent.Vibrate)
```

연결된 장치에서 사운드 재생 실행

```blocks
devices.raiseAlertTo(MesAlertEvent.PlaySound)
```

연결된 장치에서 벨 소리 재생 실행

```blocks
devices.raiseAlertTo(MesAlertEvent.PlayRingtone)
```

연결된 장치에서 내 스마트폰 찾기 실행

```blocks
devices.raiseAlertTo(MesAlertEvent.FindMyPhone)
```

연결된 장치에서 벨소리 경보 실행

```blocks
devices.raiseAlertTo(MesAlertEvent.RingAlarm)
```

## 참고 항목

[리모트 동작 명령 전송](/reference/devices/tell-remote-control-to), [카메라 동작 명령 전송](/reference/devices/tell-camera-to)

```package
devices
```