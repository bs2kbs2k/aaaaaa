# panic

오류 번호를 출력하고 프로그램 실행을 중단합니다.

```sig
control.panic(0)
```

If your board has some way to display error information, `||panic||` will work with it to show error numbers.

Your program stops when you use `||panic||`. Use this when you think something bad enough has happened and your program can't run properly anymore.

## 매개 변수

* **code**. 오류 번호를 나타내는 [수(정수)](/types/number). 프로그램에서 발생한 오류 상황을 알아낼 수 있습니다.

## 예시

Send a 'code red' error that you created to the error display if the input from pin `D0` is `false`.

```blocks
let codeRed = 1
let codeBlue = 2

if (!pins.D0.digitalRead()) {
    control.panic(codeRed)
}
```