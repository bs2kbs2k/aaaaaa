# Coding your Circuit

## @description @boardname@ 코딩하기

## ~avatar avatar

    Let's use @boardname@'s pin connection to create an electric flow to power your circuit! 
    

## ~

# 활동 소요시간: ~15분

## 블록

```cards
lights.setLevel(AnalogPin.A0, 100) 
```

## Step 1: Setting up your loop

1. Open [MakeCode](@homeurl@) in your browser. 
2. From **CONTROL**, drag a **forever** loop into your workspace. 

## Step 2: Coding your pin connection

From **LIGHTS**, drag a **set A0 to 100** block out and place it into your forever loop.

```block
loops.forever(function () {
    lights.setLevel(AnalogPin.A0, 100)
})
```

### 블록 만들기...

Change the pin value of the **set** block from `A0` to `A1`.

```block
lights.setLevel(AnalogPin.A1, 100)
```

So, now we have:

```blocks
loops.forever(function () {
    lights.setLevel(AnalogPin.A1, 100)
})
```

## 완성되었습니다!

Good work! By setting the value to a high number such as 100, it means that the current of power will be strong enough to light up a LED. Using your paper fold switch, try to turn your LED on and off. Does it work?