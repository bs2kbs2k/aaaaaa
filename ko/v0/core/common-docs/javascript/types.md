# 데이터형

유용한 프로그램들을 만들기 위해, 가장 간단한 단위 데이터들을 다룰 수 있어야 합니다.: 수, 문자열, 구조체, 불(참/거짓) 값 등

## 데이터형 자동 판별

타입스크립트에서는, 데이터형에 대한 명확한 표시가 없는 상황에서, 데이터형 정보가 자동으로 판별되는 여러 위치가 있습니다. 예를 들어, 다음 코드에서

```typescript
let x = 3;
let y = x + 3
```

`x` 변수의 데이터형은 `수`로 판별됩니다. 비슷한 방식으로, `y` 변수의 데이터형도 `수`로 판별됩니다. 이러한 형태의 데이터형 자동 판별은, 일반 변수와 구조체 멤버 변수에 저장되어있는 값을 초기화 할 때, 매개 변수의 초깃값을 설정할 때, 함수가 리턴하는 값의 데이터형을 분석해 낼 때 동작합니다.

아래의 모든 예시들은 데이터형을 함께 명시해 작성했지만, 데이터형을 명시하지 않아도 똑같이 동작합니다.

## 불(참/거짓) 논리

가장 기본적인 데이터형은, `불형(boolean, 불리언)`이라고 부르는 간단한 값인 참(true)/거짓(false) 입니다.

```typescript
let isDone: boolean = false;
```

## 수형(Number)

### ~ hint

자바스크립트에서, `수`들은 실수(floating point)값으로 처리됩니다. 하지만, @boardname@ 를 위해서는, `수`들이 정수(integer)값으로 처리됩니다.

### ~

정수값은 10진수(decimal), 16진수(hexadecimal), 8진수(octal) 표기법으로 표현할 수 있습니다.

```typescript
let decimal: number = 42;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
```

## 문자열

다른 프로그래밍언어와 마찬가지로, 텍스트 데이터들을 처리하기 위해 `문자열` 데이터형을 사용할 수 있습니다. 큰 따옴표 (`"`)나 작은 따옴표 (`'`)로 묶어 문자열을 표현할 수 있습니다.

```typescript
let color: string = "blue";
color = 'red';
```

또한, *템플릿 문자열*을 사용하면, 여러 줄 문자열과 내장 표현식(embedded expression)을 사용할 수 있습니다. 이 문자열들은 액센트그레이브/역따옴표 (`` ` ``) 기호를 사용해 표현할 수 있으며, `${ expr }`과 같은 내장 표현식도 사용할 수 있습니다.

```typescript
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${ fullName }.

I'll be ${ age + 1 } years old next month.`
```

위 코드는 다음 `sentence`과 같이 선언할 수도 있습니다.:

```typescript
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = "Hello, my name is " + fullName + ".\n\n" +
    "I'll be " + (age + 1) + " years old next month."
```

# 배열

배열을 사용하면, 순서대로 값들을 연결해 확장해가면서 작업할 수 있습니다. 각각의 값들은 정수 참조번호(index, 위치)를 이용해 접근할 수 있습니다. 배열형은 2가지 방법으로 작성할 수 있습니다. 첫 번째 방법은, 데이터 배열임을 나타내는 `[]`를 함께 붙여 표현하는 방법입니다.

```typescript
let list: number[] = [1, 2, 3];
```

두 번째 방법은, 배열형 표시자, `Array<elemType>`를 사용하는 것입니다.:

```typescript
let list: Array<number> = [1, 2, 3];
```

### ~hint

@boardname@를 위해서는, 배열에 저장되는 값들이 모두 같은 데이터형이어야 합니다.

### ~

## 열거형(Enum)

자바스크립트에서 제공되는 표준 데이터형 집합 이외에, `열거형(enum)` 데이터형이 있습니다. C# 언어에서처럼, 수를 대신해 보다 익숙한 이름을 참조번호로 사용할 수 있습니다.

```typescript
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```

기본적으로, 열거형은 첫 원소를 `0`부터 시작해 자동으로 번호가 메겨집니다. 열거형 데이터의 순서 번호를 수동으로 바꿀 수도 있습니다. 예를 들어, 이전 예시에서 `0`대신 `1`로 시작하도록 할 수도 있습니다.:

```typescript
enum Color {Red = 1, Green, Blue}
let c: Color = Color.Green;
```

또는, 심지어 각 요소의 번호를 모두 다르게 수동으로 지정할 수도 있습니다.:

```typescript
enum Color {Red = 1, Green = 2, Blue = 4}
let c: Color = Color.Green;
```

## 아무거나형(any)

타입스크립트에서, `any` 데이터형은 @boardname@에서 지원되지 않습니다.

## 빈데이터형(void)

`void`는 데이터형을 전혀 가지지 않는다는 것을 표현하는 것입니다. 일반적으로, 값을 리턴하지 않는 함수의 데이터형으로 사용되는 것을 자주 볼 수 있습니다.

```typescript
function warnUser(): void {
    basic.showString("This is my warning message");
}
```

`void` 형으로 변수를 선언하는 것은 쓸모가 없습니다.