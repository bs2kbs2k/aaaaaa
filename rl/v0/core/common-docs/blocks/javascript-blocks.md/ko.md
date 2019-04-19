# 자바스크립트 블록

자바스크립트는 매우 강력한 프로그래밍언어입니다.; 그렇기 때문에 블록으로 만들 수 없는 기능들도 가능합니다. PXT 가 블록으로 변경할 수 없는 코드를 만나면, 그 코드를 회색의 자바스크립트 블록으로 바꿉니다. 텍스트 편집기 환경으로 바뀌면, 회색 블록들은 원래의 자바스크립트 코드로 바뀌며 복구됩니다.

```block
for (let index = 0; index <= 5; index++) {
    let x = fibonacci(index);
}

function fibonacci(n: number): number {
    if (n === 0 || n === 1) {
        return 1;
    }

    return fibonacci(n - 1) + fibonacci(n - 2);
}
```

자바스크립트 블록 상태에서의 코드는 편집이 불가능합니다. 하지만, 다른 블록들과 마찬가지로 이동, 복사, 붙여넣기, 삭제 가 됩니다.

## 어떻게 하면, 자바스크립트 코드를 회색 블록 없이 모두 변환시킬 수 있을까요?

가장 쉬운 방법은, 블록 환경과 자바스크립트 환경을 번갈아 바꾸어가면서 코드를 작성해가는 것입니다. 많은 블록들은, 정상적으로 해당 자바스크립트로 변환시키는데 필요한 매우 특별한 구조를 가지고 있습니다. 변환되지 않는 코드를 포함한 부분이 있다면, 자바스크립트로 만들어질 것이라고 생각하며 자세히 블록을 살펴봐야 합니다.

예를 들어, for-반복 구조가 블록으로 변환되기 위해서는 다음과 같은 구조가 포함되어 있어야 합니다.:

```typescript
for (let x = 0; x <= 5; x++) {
}
```

다음 예시들은 정상적인 블록으로 바뀌지 않습니다.:

```typescript-ignore
// Condition must be either < or <= with a variable on the left side
for (let x = 0; x > -1; x++) {
}

// The both the variable in the condition and the variable with increment
// operator must be the same as the declared variable
for (let x = 0; x <= 5; y++) {
}

// The declared variable must be initialized to 0
for (let x = 2; x <= 5; x++) {
}

// All three parts of the for-loop must be present
for (;;) {
}
```

자바스크립트와 블록의 위치를 최대한 가깝게 맞춰 두세요.