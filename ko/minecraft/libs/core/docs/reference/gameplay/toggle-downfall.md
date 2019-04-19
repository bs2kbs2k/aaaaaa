# Toggle Downfall

Start raining if isn't raining. Stop the rain when it is raining.

```sig
gameplay.toggleDownfall();
```

## 예시

Create a strange weather pattern.

```blocks
for (let i = 0; i < 4; i++) {
    gameplay.toggleDownfall()
    loops.pause(Math.randomRange(0, 5) * 1000)
    gameplay.toggleDownfall()
    loops.pause(Math.randomRange(0, 5) * 1000)
}
```