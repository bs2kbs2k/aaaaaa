# Call a function

The simplest way to get started in JavaScript with your @boardname@ is to call one of the @boardname@'s built-in JavaScript functions. Just like how Blocks are organized into categories/drawers, the @boardname@ functions are organized by namespaces, with names corresponding to the drawer names.

```typescript-ignore
Math.abs(-1)
```

### ~ hint

If you want to see all functions available in the `Math` namespace, simply type `Math` followed by `.` and a list of all the functions will appear.

### ~

## Left and right parentheses, please!

Whenever you want to call a function, you give the name of the function followed by `(` and ending with `)`. In between the left and right parentheses go the function arguments:

```typescript-ignore
Math.min(1, 2)
```

It's a syntax error to have a left parenthesis without the "closing" right parenthesis:

```typescript-ignore
Math.min(
```

함수에 전달하는 매개 변수나 값이 없을 때에도, 함수를 호출하기 위해 소괄호()를 함께 사용해야 합니다.

## Any results for me?

Many functions return a result for you to use later in your program. This might be a number, a string, or another type of data.

```typescript-ignore
let greater = Math.max(5, 10)
```