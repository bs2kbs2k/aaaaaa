# 만들기

여러 개의 값들을 저장할 수 있는 배열을 만듭니다.

## 배열 만들기

### 빈 배열

데이터가 저장되어있지 않은 빈 배열을 만들 수 있습니다. 배열을 만들기 위해서는 배열에 저장할 [데이터형](/types)을 함께 작성해 주어야 합니다. 문자열을 저장할 수 있는 빈 배열은 다음과 같이 만들 수 있습니다.:

```typescript
let empty: string[] = []
```

```blocks
let empty: string[] = []
```

### 데이터 1개 배열

데이터 1개를 저장해 *초기화*하며, 배열을 만들 수 있습니다. 데이터 1개를 저장하며 배열을 선언해 만들면, 자동으로 저장된 데이터의 [데이터형](/types)으로 배열이 생성됩니다. 이러한 기능을 *데이터형 자동 판별(type inference)*이라고 합니다.

```block
let oneItem = ["item"]
```

### 여러 개 데이터 배열

필요한 경우, 1개 이상의 데이터를 저장시켜 초기화하며 배열을 만들 수 있습니다.

```block
let twoItems = [1, 2]
```

## 예시

수 값들을 저장할 수 있는 배열을 만든 다음, 그 배열에 2개의 수를 추가합니다.

```blocks
let scores: number[] = [];
scores.push(98);
scores.push(75);
let lastScore = scores.pop();
```

2개의 단어를 저장시켜 초기화한 배열을 만든 다음, 두 단어가 저장되어있는 위치를 서로 바꿉니다.

```blocks
let words = ["Hello", "there"]
let swap = words[0];
words[0] = words[1];
words[1] = swap;
```