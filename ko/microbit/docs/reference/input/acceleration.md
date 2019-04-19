# 가속도 센서 값

3축(x, y, z) 방향으로 따로 따로 가속도 크기를 측정하거나, 3축 방향의 가속도 합벡터 크기를, 밀리g(milli g) 단위의 값으로 측정할 수 있습니다.

@boardname@ 보드의 움직임과 이동에 따른 가속도(속도가 빨라지거나 느려지는 속도 변화 값) 크기를 측정해보세요.

```sig
input.acceleration(Dimension.X);
```

## ~hint

밀리g(**milli-g**) 단위로 가속도를 측정할 수 있습니다. 밀리g는 중력가속도 **g** 의 1/1000 단위입니다. **1g** 는 지구에서 어떤 물체가 중력의 힘을 받아 떨어질 때의 시간에 따른 속도변화(가속도)를 의미합니다.

## ~

## 매개 변수

* **기준 방향**: 가속도를 측정하려는 기준 방향 축. 또는 3축 방향의 합 가속도 크기. >`x`: acceleration in the left and right direction.  
    `y`: acceleration in the forward and backward direction.  
    `z`: acceleration in the up and down direction.  
    `strength`: the resulting strength of acceleration from all three dimensions (directions).

### ~hint

**Forces in space**

Since we don't live on a flat world, forces happen in three dimensional space. If the movement of an object isn't exactly in the direction of one axis, we need a way to calculate its acceleration from the values measured for all the axes together.

If you put your @boardname@ on a level table and push it diagonally, you have an acceleration in two dimensions. You can find the acceleration in that direction just like how you calculate the long side of a triangle using the two shorter sides (**X** and **Y**):

    strength2D = Math.sqrt((accelX * accelX) + (accelY * accelY))

If you decide to lift your @boardname@ off the table, then you've just added another dimension, so insert the acceleration value for the **Z** axis into the equation:

    strength3D = Math.sqrt((accelX * accelX) + (accelY * accelY) + (accelZ * accelZ))

This calculation is called the [Euclidean norm](https://en.wikipedia.org/wiki/Euclidean_norm) of acceleration.

### ~

## 리턴값

* [정수](/types/number). 가속도의 크기. @boardname@ 의 앞면을 하늘 쪽을 향하도록 바닥에 내려놓으면, `x축 방향` 가속도는 `0`, `y축 방향` 가속도는 `0`, `z축 방향` 가속도는 `-1023` 으로 측정되며, 3축 방향 가속도의 (벡터)합 `크기` 는 `1023`이 됩니다.

## 예시: LED 그래프

다음 코드는 @boardname@ 의 가속도를 LED 그래프로 출력해주는 예시입니다.

```blocks
basic.forever(() => {
    led.plotBarGraph(input.acceleration(Dimension.X), 1023)
})
```

### Example: quake meter

Every 5 seconds, with the @boardname@ facing upward on a flat surface, show how much the earth is shaking (if at all).

```blocks
basic.forever(() => {
    basic.showNumber(input.acceleration(Dimension.Strength))
    basic.pause(5000)
})
```

## 참고 항목

[가속도 센서 감지 값 설정](/reference/input/set-accelerometer-range), [자기(나침반) 센서 각도](/reference/input/compass-heading), [LED 스크린 빛 센서 밝기](/reference/input/light-level)