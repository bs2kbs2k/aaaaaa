# show Mood

Show a mood on the brick. A mood will have a image on the display along with a sound and solid or flashing light.

```sig
brick.showMood(moods.sleeping)
```

You can choose one of several moods to show on the display. Use a mood to help show what your @boardname@ is doing at the moment.

## 매개 변수

**mood**: A mood to show on the brick. Choose one of these moods:

> * `sleeping`

* `awake`
* `tired`
* `화남`
* `슬픔`
* `dizzy`
* `knockedOut`
* `middleLeft`
* `middleRight`
* `love`
* `winking`
* `neutral`

## 예시

Show a `winking` mood on the brick.

```blocks
brick.showMood(moods.winking)
```

## 참고 항목

[show image](/reference/brick/show-image)