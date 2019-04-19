# 순차 실행

순서대로 함수를 호출하면서 실행할 때, 상황에 따라 다르게 실행되도록 할 수 있습니다.

```typescript-ignore
doSomething();
doAnotherThing();
```

## The semicolon

자바스크립트에서, 세미콜론(;)은 명령문의 마지막을 나타내는 의미로 사용됩니다. 하지만, 대부분의 경우 세미콜론 기호를 옵션으로 생략해도 됩니다. 따라서, 다음과 같은 순차 실행 코드가 모두 가능합니다.:

```typescript-ignore
doSomething()
doAnotherThing()
```

```typescript-ignore
doSomething();
doAnotherThing();
```

## The empty statement

자바스크립트에는, *공문(empty statement)* 개념이 있습니다. 공문은 명령 없이 빈 공백 다음에 세미콜론을 작성하는 것을 말합니다. 따라서, 다음 코드에서 무한 반복 실행 명령문 다음에 있는 `doSomething` 명령은 영원히 실행되지 않게 됩니다.:

```typescript-ignore
while(true) ;
doSomething(); // 영원히 실행되지 않음!
```

### ~hint

이러한 문제 상황을 피하기 위해서, 위와 같은 실행 명령 없는 공문(empty statement)은 허용되지 않습니다. 하지만, 공문을 사용해야하는 경우에는, 중괄호 기호{}를 사용해 공문 부분을 코드 블록으로 묶어주면 됩니다.

```typescript-ignore
while(true) { } 
doSomething(); // 영원히 실행되지 않음!
```

### ~

[자바스크립트에서의 세미콜론(;) 기호에 대해서 더 살펴보세요](http://inimino.org/~inimino/blog/javascript_semicolons).