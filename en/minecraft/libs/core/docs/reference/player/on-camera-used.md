# on Camera Used

Runs code when a picture is taken with a camera.

```sig
player.onCameraUsed(() => {

});
```

## Parameters

* **handler**: code to run when the camera is used

## Example

Remind players to smile to the camera!

```blocks
player.onCameraUsed(() => {
    player.say("Smile, you're on camera!");
});
```