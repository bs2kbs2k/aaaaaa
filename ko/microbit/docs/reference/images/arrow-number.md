# 화살표 번호

화살표 이미지와 쌍으로 맞춰져 있는 화살표 번호를 가져옵니다.

```sig
images.arrowNumber(ArrowNames.North)
```

각각의 화살표 이미지는 고유한 번호 값이 할당되어있습니다. `||Images:arrow number||` 를 사용하면 화살표 이미지에 따른 번호 값을 알아낼 수 있습니다.

## 매개 변수

* **화살표 방향**: 번호 값을 알아내고자 하는 화살표 방향. 다음과 같은 방향이름 사용 가능:

> * `북쪽`

* `북동쪽`
* `동쪽`
* `남동쪽`
* `남쪽`
* `남서쪽`
* `서쪽`
* `북서쪽`

## 예시

다음은 `남쪽` 화살표 이미지에 대한 번호를 알아내는 예시 코드입니다.

```blocks
let arrowSouthNumber = images.arrowNumber(ArrowNames.South)
```

## 참고 항목

[arrow image](/reference/images/arrow-image)