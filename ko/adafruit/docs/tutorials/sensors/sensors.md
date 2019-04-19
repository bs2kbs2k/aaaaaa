## 단계 1

Let's explore some of the sensors on the @boardname@, starting with the Motion Sensor. The Motion Sensor measures Acceleration along 3 dimensions: X-axis (left and right), Y-axis (forward and backward), and the Z-axis (up and down). 측정값의 범위는 -1023에서 +1023 입니다. When the @boardname@ is laying flat: X = 0, Y = 0, Z = -1023.

![Circuit Playground Accelerometer](/BoardAccelerometer.png)

## 단계 2

Open the **Light** Toolbox drawer, and click on **More** subcategory. Drag the `||graph||` block onto your programming Workspace, and put it in the `||forever||` loop.

```blocks
forever(() => {
    light.graph(
    0,
    0
    )
})
```

![Graph block](/graphblock.gif)

## 단계 3

Open the **Input** Toolbox drawer, drag the `||acceleration||` block into the first slot of the `||graph||` block.

```blocks
forever(() => {
    light.graph(
    input.acceleration(Dimension.X),
    0
    )
})
```

![Acceleration block](/accelerationblock.gif)

## 단계 4

Set the maximum value to `1023` by typing this number into the second slot of the `||graph||` block.

```blocks
forever(() => {
    light.graph(
    input.acceleration(Dimension.X),
    1023
    )
})
```

![Graph Acceleration block](/graph-acceleration.png)

## 단계 5

Test your program in the Simulator by moving the mouse across the @boardname@ from left to right. 이제 `|Download|` 를 눌러 프로그램 코드를 @boardname@ 에 업로드하세요. Next, you can try measuring acceleration along the Y and Z axis.

![시뮬레이터에서의 가속도](/SimulatorAcceleration.gif) ![Hardware Acceleration](/HardwareAcceleration.gif)

## 단계 6

Now let's look at the Light Sensor on the @boardname@.  
The @boardname@ measures how light or dark it is through a light level sensor where 0 = completely dark, and 255 = bright light.

![Circuit Playground Light Sensor](/BoardLightSensor.png)

## 단계 7

From your existing Motion Sensor program, delete the `||acceleration||` block by dragging it to the Toolbox area.

![블록 삭제](/deleteacceleration.gif)

## Step 8

Open the **Input** Toolbox drawer, drag the `||light level||` block into the first slot of the `||graph||` block.

```blocks
forever(() => {
    light.graph(
    input.lightLevel(),
    1023
    )
})
```

![Light level block](/lightlevelblock.gif)

## Step 9

Set the maximum value to `255` by typing this number into the second slot of the `||graph||` block.

```blocks
forever(() => {
    light.graph(
    input.lightLevel(),
    255
    )
})
```

![Graph Light level block](/graph-lightlevel.png)

## 단계 10

Test your program in the Simulator by changing the light level meter. Now click `|Download|` to transfer your code to the @boardname@.

![시뮬레이터에서의 빛 밝기](/SimulatorLightLevel.gif) ![Hardware Light Level](/HardwareLightLevel.gif)