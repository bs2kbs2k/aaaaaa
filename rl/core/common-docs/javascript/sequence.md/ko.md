# Sequencing

순서대로 함수를 호출하면서 실행할 때, 상황에 따라 다르게 실행되도록 할 수 있습니다.

```typescript-ignore
doSomething();
doAnotherThing();
```

## The semicolon

In JavaScript, the semicolon (;) is used to terminate (or end) a statement. However, in most cases, the semicolon is optional and can be omitted. So both code sequences below are legal:

```typescript-ignore
doSomething()
doAnotherThing()
```

```typescript-ignore
doSomething();
doAnotherThing();
```

## The empty statement

In JavaScript, there is the concept of an *empty statement*, which is whitespace followed by a semicolon in the context where a statement is expected. 따라서, 다음 코드에서 무한 반복 실행 명령문 다음에 있는 `doSomething` 명령은 영원히 실행되지 않게 됩니다.:

```typescript-ignore
while(true) ;
doSomething(); // 영원히 실행되지 않음!
```

### ~hint

이러한 문제 상황을 피하기 위해서, 위와 같은 실행 명령 없는 공문(empty statement)은 허용되지 않습니다. If you really want an empty statement, you need to use curly braces to delimit an empty statement block:

```typescript-ignore
while(true) { } 
doSomething(); // 영원히 실행되지 않음!
```

### ~

[자바스크립트에서의 세미콜론(;) 기호에 대해서 더 살펴보세요](http://inimino.org/~inimino/blog/javascript_semicolons).