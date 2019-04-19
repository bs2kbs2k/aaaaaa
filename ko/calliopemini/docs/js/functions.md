# 함수

Functions are the fundamental building block of programs. Here is the simplest way to make a function that adds two numbers:

```ts
// Named function
function add(x : number, y : number) {
    return x + y;
}

basic.showNumber(add(1, 2))
```

### ~ hint

For the @boardname@, you must specify a [type](/js/types) for each function parameter.

### ~

Functions can refer to variables outside of the function body. When they do so, they're said to `capture` these variables.

```ts
let z = 100;

function addToZ(x: number, y: number) {
    return x + y + z;
}

basic.showNumber(addToZ(1, 2))
```

## Typing the function

Let's add a return type to our add function:

```ts
function add(x: number, y: number): number {
    return x + y;
}
```

TypeScript can figure the return type out by looking at the return statements, so you can optionally leave this off in many cases.

# 옵션 및 디폴트 매개 변수들

타입스크립트 프로그래밍언어에서, 어떤 함수로 전달되는 매개 변수나 값의 개수는 일치되어야 합니다.

```ts-ignore
function buildName(firstName: string, lastName: string) {
    return firstName + " " + lastName;
}

let result1 = buildName("Bob");                  // 오류 발생, 매개 변수 개수 적음
let result2 = buildName("Bob", "Adams", "Sr.");  // 오류 발생, 매개 변수 많음
let result3 = buildName("Bob", "Adams");         // 오류 없음
```

자바스크립트에서, 매개 변수들은 옵션이기 때문에, 비워두고 사용할 수 있습니다. 그렇게 하면, 그 값들은 `정의되지않은(undefined)` 임의의 값을 가지게 됩니다. 타입스크립트에서는, 옵션으로 처리 할 매개 변수들의 마지막에 `?` 기호를 붙여, 이러한 기능이 동작하도록 할 수 있습니다. 예를 들어, 위에서 작성한 마지막 매개 변수를 옵션으로 처리하고 싶다면:

```ts-ignore
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

```ts-ignore
function buildName(firstName: string, lastName = "Smith") {
    return firstName + " " + lastName;
}

let result1 = buildName("Bob");                  // 정상적으로 동작하게 됨, "Bob Smith" 리턴
let result2 = buildName("Bob", undefined);       // 정상 동작함, "Bob Smith" 리턴
let result3 = buildName("Bob", "Adams", "Sr.");  // 오류 발생, 매개 변수 많음
let result4 = buildName("Bob", "Adams");         // 오류 없음
```

디폴트-초기화 매개 변수는, 모든 매개 변수들이 옵션으로 취급될 때 값이 저장되며, 옵션 매개 변수와 같이, 함수가 호출 될 때 그 값이 전달됩니다. 따라서, 옵션 매개 변수와 디폴트 매개 변수의 값을 바꾸는 것은, 같은 데이터형을 공유하게 됩니다. 따라서 다음과 같은 것이 가능합니다.

```ts
function buildName(firstName: string, lastName?: string) {
    // ...
}
```

and

```ts
function buildName(firstName: string, lastName = "Smith") {
    // ...
}
```

같은 데이터형 `(firstName: string, lastName?: string) => string` 을 공유합니다. `lastName` 의 디폴트 값은 데이터형이 사라지며, 매개 변수가 옵션이라는 사실만 남게 됩니다.

일반 옵션 매개 변수와 다르게, 디폴트-초기화 매개 변수는 매개 변수의 값을 전달 받은 후 개체가 생성될 *필요*가 없습니다. 만약 디폴트-초기화 매개 변수가, 필수 매개 변수 앞에 놓이면, 디폴트로 초기화 할 값을 명시적으로 `정의되지않은(undefined)` 상태로 전달해야 합니다. 예를 들어, 마지막 예시의 `firstName`에 대해서만 디폴트-초기화 매개 변수로 작성할 수 있습니다.:

```ts-ignore
function buildName(firstName = "Will", lastName: string) {
    return firstName + " " + lastName;
}

let result1 = buildName("Bob");                  // 오류 발생, 매개 변수 적음
let result2 = buildName("Bob", "Adams", "Sr.");  // 오류 발생, 매개 변수 많음
let result3 = buildName("Bob", "Adams");         // 오류 없음, "Bob Adams" 리턴
let result4 = buildName(undefined, "Adams");     // 오류 없음, "Will Adams" 리턴
```

# Rest Parameters

Required, optional, and default parameters all have one thing in common: they talk about one parameter at a time. Sometimes, you want to work with multiple parameters as a group, or you may not know how many parameters a function will ultimately take. In JavaScript, you can work with the arguments directly using the `arguments` variable that is visible inside every function body.

In TypeScript, you can gather these arguments together into a variable:

```ts-ignore
function buildName(firstName: string, ...restOfName: string[]) {
    return firstName + " " + restOfName.join(" ");
}

let employeeName = buildName("Joseph", "Samuel", "Lucas", "MacKinzie");
```

*Rest parameters* are treated as a boundless number of optional parameters. When passing arguments for a rest parameter, you can use as many as you want; you can even pass none. The compiler will build an array of the arguments passed in with the name given after the ellipsis (`...`), allowing you to use it in your function.

The ellipsis is also used in the type of the function with rest parameters:

```ts-ignore
function buildName(firstName: string, ...restOfName: string[]) {
    return firstName + " " + restOfName.join(" ");
}

let buildNameFun: (fname: string, ...rest: string[]) => string = buildName;
```

### ~button /js/types

NEXT: Types

### ~