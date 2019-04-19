# Send Buffer

Sends a buffer to other @boardname@s in the area connected by radio. The maximum buffer length is 19 bytes.

```sig
radio.sendBuffer(pins.createBuffer(1))
```

## 매개 변수

* `msg` is a [buffer](/types/buffer) to send by radio.

## Example: Remote level

If you load this program onto two @boardname@s, each board will send the level information to the other board.

```typescript
let ax = 0;
let ay = 0;
basic.forever(() => {
    ax = input.acceleration(Dimension.X);
    ay = input.acceleration(Dimension.Y);

    // encode data in buffer
    let buf = pins.createBuffer(4)
    buf.setNumber(NumberFormat.Int16LE, 0, ax)
    buf.setNumber(NumberFormat.Int16LE, 2, ay)
    radio.sendBuffer(buf)
})

radio.onDataPacketReceived(({ receivedBuffer }) => {
    // decode data from buffer
    ax = receivedBuffer.getNumber(NumberFormat.Int16LE, 0);
    ay = receivedBuffer.getNumber(NumberFormat.Int16LE, 2);

    // display
    basic.clearScreen()
    led.plot(
        pins.map(ax, -1023, 1023, 0, 4),
        pins.map(ay, -1023, 1023, 0, 4)
    )
});
```

## ~hint

라디오 데이터를 전송하면서 동시에 수신할 수 있는 장치를 *트랜시버(transceiver)* 라고도 부릅니다.

## ~

## 참고 항목

[on data packet received](/reference/radio/on-data-packet-received)

```package
라디오
```