# analog Set Period

Use this time period for servo commands and other PWM signals.

```sig
pins.A1.analogSetPeriod(20000)
```

With *Pulse Width Modulation (PWM)*, a pulse signal is sent regularly, many times a second. How many times a pulse is sent in each second decides what period it has. If a *pwm* signal is sent 50 times a second, then its period is 1/20th of a second which is 20 milliseconds.

You use microseconds for the amount of time you set your *pwm* signal period. One second is a million microseconds and 1 millisecond is 1000 microseconds.

## 매개 변수

* **period**: a [number](types/number) that is the period for the pulse signal sent at the pin.

## 예시 #ex1

Set the period for a PWM signal to 20 milliseconds.

```blocks
pins.A1.analogSetPeriod(20000)
```

## 참고 항목

[`||servo write||`](/reference/pins/servo-write), [`||servo set pulse||`](/reference/pins/servo-set-pulse)

[What is PWM?](/reference/pins/what-is-pwm)