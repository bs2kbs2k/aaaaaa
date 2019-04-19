# 네트워크

Send and receive data between your @boardname@ and another board.

## 케이블

```cards
network.cableSendNumber(0);
network.onCableReceivedNumber(function (num) { })
```

## 적외선

```cards
network.infraredSendNumber(0);
network.onInfraredReceivedNumber(function (num) { })
```

## 참고 항목

[cable send number](/reference/network/cable-send-number), [on cable received number](/reference/network/on-cable-received-number), [infrared send number](/reference/network/infrared-send-number), [on infrared received number](/reference/network/on-infrared-received-number)

```package
cable
infrared
```