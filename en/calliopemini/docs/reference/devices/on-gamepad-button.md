# On Gamepad Button

Register code to run when the @boardname@ receives a command from the paired gamepad.

### ~hint

The functions in the `devices` namespace allow the @boardname@ to communicate with a separate (remote) device, such as a smartphone, over Bluetooth (Smart). The set of supported events will depend on the remote device and the @boardname@ apps available for the remote device.

### ~

```sig
devices.onGamepadButton(MesDpadButtonInfo.ADown, () => {})
```

### Parameters

* `body`: Action code to run when the the @boardname@ receives a command from the paired gamepad.

### See Also

[tell remote control to](/reference/devices/tell-remote-control-to), [raise alert to](/reference/devices/raise-alert-to), [signal strength](/reference/devices/signal-strength), [on signal strength changed](/reference/devices/on-signal-strength-changed)

```package
devices
```