# @extends

## #examples

## 예시: `AND` 연산자

다음은 `1 , 1` 와 `2 , 2` 위치의 LED가 둘 다 모두 켜져있을 때, `3 , 3` 위치의 LED를 켜는 예시입니다.:

```blocks
if (led.point(1,1) && led.point(2,2)) {
   led.plot(3,3)
}
```

## 예시: 수/문자열의 비교

어떤 두 수를 서로 비교하면, 그 계산 결과로 참(true) 또는 거짓(false)의 불 값을 얻게 됩니다. 다음 코드에서 `x < 5` 비교식을 살펴보세요.:

```blocks
input.onButtonPressed(Button.A, () => {
    let x = Math.random(5)
    if(x < 5) {
    basic.showString("low");
    } else { 
    basic.showString("high");
    }
})
```

두 수(정수)를 비교하는 것에 대해서 더 자세히 알고싶다면, [수(정수)](/types/number) 문서를 살펴보세요.