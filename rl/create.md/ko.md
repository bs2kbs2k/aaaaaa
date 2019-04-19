# 만들기

여러 개의 값을 저장할 수 있는 배열을 만듭니다.

## 배열 만들기

### 빈 배열

You can create arrays with no items. If you do that, you'll need tell what [type](/types) the array will be. This is an empty array:

```typescript
let empty: string[] = []
```

```blocks
let empty: string[] = []
```

### 데이터 1개 배열

You can create and *initialize* an array with an item. Arrays created with at least one item automatically have the [type](/types) of the item. This is called a *type inference*.

```block
let oneItem = ["item"]
```

### 여러 개 데이터 배열

필요한 경우, 1개 이상의 데이터를 저장하여 초기화한 배열을 만들 수 있습니다.

```block
let twoItems = [1, 2]
```

## 예시

Make an empty array of numbers. Then, add two numbers to the array.

```blocks
let scores: number[] = [];
scores.push(98);
scores.push(75);
let lastScore = scores.pop();
```

Make an array with two words, then swap them in the array.

```blocks
let words = ["Hello", "there"]
let swap = words[0];
words[0] = words[1];
words[1] = swap;
```