# play Sound Effect

Play a sound from one of the built-in sound effects.

```sig
music.playSoundEffect(null)
```

There are several sound effects you can play. Use the sounds list in the block to pick the sound you want to play. When the sounds starts, your program continues on and doesn't wait for the sound to finish. This lets your program do other things while your sound plays in the *background*.

Many of the built-in sound effects make sounds match to the actions that your @boardname@ is doing. For example, you can add the `mechanical motor start` sound to your program to indicate that your motors are running.

## 매개 변수

* **sound**: a built-in sound effect from the list of available sounds.

## 예시

Drive the brick backwards and play a backup alert sound.

```blocks
music.playSoundEffect(sounds.mechanicalBackingAlert);
motors.largeBC.tank(-50, -50, 15, MoveUnit.Rotations);
music.stopAllSounds();
```

## 참고 항목

[play sound effect until done](/reference/music/play-sound-effect-until-done), [stop all sounds](/reference/music/stop-all-sounds)