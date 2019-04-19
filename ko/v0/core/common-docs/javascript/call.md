# 함수 호출

여러분의 @boardname@ 을 이용해 자바스크립트를 시작하는 가장 쉬운 방법은 @boardname@에 내장된 자바스크립트 함수를 호출하는 것입니다. Just like how Blocks are organized into categories/drawers, the @boardname@ functions are organized by namespaces, with names corresponding to the drawer names.

```typescript
Math.abs(-1)
```

### ~ hint

`Math` 명칭공간에서 사용이 가능한 모든 함수를 보고싶을 때에는, `Math` 입력 후 `.` 을 누르면 사용 가능한 모든 함수들이 나타나게 됩니다.

### ~

## 왼쪽 오른쪽 괄호를 반드시 쌍으로 사용하세요!

Whenever you want to call a function, you give the name of the function followed by `(` and ending with `)`. In between the left and right parentheses go the function arguments:

```typescript
Math.min(1, 2)
```

시작하는 왼쪽 괄호와 "끝내는" 오른쪽 괄호를 함께 사용하지 않으면, 문법적 오류가 발생하게 됩니다.

```typescript-ignore
Math.min(
```

함수에 전달하는 매개 변수나 값이 없을 때에도, 함수를 호출하기 위해 소괄호()를 함께 사용해야 합니다.

## Any results for me?

Many functions return a result for you to use later in your program. This might be a number, a string, or another type of data.

```typescript
let greater = Math.max(5, 10)
```