# 함수

함수는 프로그램을 만드는 기본적인 빌딩 블록이라고 할 수 있습니다. 2개의 수를 더하는 가장 간단한 함수를 만드는 방법은 다음과 같습니다.:

```typescript
// 이름을 붙인 함수
function add(x : number, y : number): number {
    return x + y;
}

let sum = add(1, 2);
```

### ~ hint

@boardname@을 위해서는, 함수에 전달하는 매개 변수 각각의 [데이터형](/javascript/types)을 정확히 작성해 주어야합니다.

### ~

함수 안에서는 함수 밖에서 정의된 변수들을 참조할 수 있습니다. 그렇게 하면, 함수 외부에 있는 변수들을 참조해 `값을 가져오게` 됩니다.

```typescript
let z = 100;

function addToZ(x: number, y: number) {
    return x + y + z;
}

let sum = addToZ(1, 2);
```

만든 함수에 의해 리턴되는 값에 대한 데이터형을 추가해야합니다.:

```typescript
function add(x: number, y: number): number {
    return x + y;
}
```

타입스크립트(TypeScript) 프로그래밍언어에서는 리턴 명령에 의해서 리턴되는 값의 데이터형을 자동으로 판단할 수 있습니다. 그렇기 때문에 많은 경우에 생략할 수 있습니다.

## 옵션 및 디폴트 매개 변수들

타입스크립트 프로그래밍언어에서, 어떤 함수로 전달되는 매개 변수나 값의 개수는 일치되어야 합니다.

```typescript-ignore
function buildName(firstName: string, lastName: string) {
    return firstName + " " + lastName;
}

let result1 = buildName("Bob");                  // 오류 발생, 매개 변수 개수 적음
let result2 = buildName("Bob", "Adams", "Sr.");  // 오류 발생, 매개 변수 많음
let result3 = buildName("Bob", "Adams");         // 오류 없음
```

자바스크립트에서, 매개 변수들은 옵션이기 때문에, 비워두고 사용할 수 있습니다. 그렇게 하면, 그 값들은 `정의되지않은(undefined)` 임의의 값을 가지게 됩니다. 타입스크립트에서는, 옵션으로 처리 할 매개 변수들의 마지막에 `?` 기호를 붙여, 이러한 기능이 동작하도록 할 수 있습니다. 예를 들어, 위에서 작성한 마지막 매개 변수를 옵션으로 처리하고 싶다면:

```typescript-ignore
function buildName(firstName: string, lastName?: string) {
    if (lastName)
        return firstName + " " + lastName;
    else
        return firstName;
}

let result1 = buildName("Bob");                  // 정상적으로 동작하게 됨
let result2 = buildName("Bob", "Adams", "Sr.");  // 오류 발생, 매개 변수 많음
let result3 = buildName("Bob", "Adams");         // 오류 없음
```

옵션으로 처리할 매개 변수들은 반드시, 필수 매개 변수 다음에 작성해야 합니다. 마지막 매개 변수 대신, 첫 번째 매개 변수를 옵션으로 만들고 싶은 경우, 매개 변수를 작성할 때 순서를 마지막으로 바꾸어야 합니다.

타입스크립트에서, 매개 변수로 전달되지 않은 값이나, `정의되지않은(undefined)` 상태로 둔 값을, 원하는 값으로 초기화하도록 할 수 있습니다. 이러한 방법을 디폴트-초기화 매개 변수라고 부릅니다. 이전 예시에서, 마지막 매개 변수의 값을 `"Smith"`로 기본 초기화하도록 할 수 있습니다.

```typescript-ignore
function buildName(firstName: string, lastName = "Smith") {
    return firstName + " " + lastName;
}

let result1 = buildName("Bob");                  // 정상적으로 동작하게 됨, "Bob Smith" 리턴
let result2 = buildName("Bob", undefined);       // 정상 동작함, "Bob Smith" 리턴
let result3 = buildName("Bob", "Adams", "Sr.");  // 오류 발생, 매개 변수 많음
let result4 = buildName("Bob", "Adams");         // 오류 없음
```

디폴트-초기화 매개 변수는, 모든 매개 변수들이 옵션으로 취급될 때 값이 저장되며, 옵션 매개 변수와 같이, 함수가 호출 될 때 그 값이 전달됩니다. 따라서, 옵션 매개 변수와 디폴트 매개 변수의 값을 바꾸는 것은, 같은 데이터형을 공유하게 됩니다. 따라서 다음과 같은 것이 가능합니다.

```typescript
function buildName(firstName: string, lastName?: string) {
    // ...
}
```

and

```typescript
function buildName(firstName: string, lastName = "Smith") {
    // ...
}
```

같은 데이터형 `(firstName: string, lastName?: string) => string` 을 공유합니다. `lastName` 의 디폴트 값은 데이터형이 사라지며, 매개 변수가 옵션이라는 사실만 남게 됩니다.

일반 옵션 매개 변수와 다르게, 디폴트-초기화 매개 변수는 매개 변수의 값을 전달 받은 후 개체가 생성될 *필요*가 없습니다. 만약 디폴트-초기화 매개 변수가, 필수 매개 변수 앞에 놓이면, 디폴트로 초기화 할 값을 명시적으로 `정의되지않은(undefined)` 상태로 전달해야 합니다. 예를 들어, 마지막 예시의 `firstName`에 대해서만 디폴트-초기화 매개 변수로 작성할 수 있습니다.:

```typescript-ignore
function buildName(firstName = "Will", lastName: string) {
    return firstName + " " + lastName;
}

let result1 = buildName("Bob");                  // 오류 발생, 매개 변수 적음
let result2 = buildName("Bob", "Adams", "Sr.");  // 오류 발생, 매개 변수 많음
let result3 = buildName("Bob", "Adams");         // 오류 없음, "Bob Adams" 리턴
let result4 = buildName(undefined, "Adams");     // 오류 없음, "Will Adams" 리턴
```

## 애로우(화살표) 함수

Arrow functions, also known as *lambda* functions, provide a lightweight syntax for functions. Arrow functions are used extensively to provide event handlers for many APIs. For example:

```typescript
function foo(handler: Action) {
    // call handler ...
}

foo(() => { // arrow function!
   // do something
})
```

Often, a function like `foo()` will save the arrow function `handler` in a variable to run the code inside the function later when a certain condition occurs. Arrow functions serve as a kind of shortcut to provide extra code to run without having to write a separate formal function for that purpose. In this way arrow, or lambda, functions are thought of as "anonymous" functions.

[애로우 함수에 대해서 더 알아보기...](http://devdocs.io/javascript/functions/arrow_functions)

## Anonymous Functions

Anonymous functions are used just like arrow functions. They're called "anonymous" because the function doesn't have a name and isn't called using a name. The function is used directly ("inline") or it's remembered by variable and used later by it's *reference* from the variable.

Here's an example similar to the one shown for arrow functions but this time the `foo()` function uses an anonymous function directly:

```typescript
function foo(handler: Action) {
    // call handler ...
}

foo(function() { // use an inline function
   // do something
})
```

You can set a variable to remember the function and use that variable as a reference to the anonymous function:

```typescript
function foo(handler: Action) {
    // call handler ...
}

let anon = function() { // anonymous function, set it to a variable
    // do something
}

foo(anon)
```