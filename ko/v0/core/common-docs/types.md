# 데이터형

*데이터형은* 데이터와 클래스에서 허용되는 작업이 다릅니다. @boardname@ 에서는 다음과 같은 데이터형이들이 지원됩니다.:

## 기초(기본) 데이터형 #primitives

* **[수형](/types/number)**: (32-bit 부호형) 정수(integer)
* **[문자열형](/types/string)**: 문자들을 연속적으로 연결한 데이터
* **[불형](/types/boolean)**: 참(true) 또는 거짓(false)

## 복합 데이터형 #complex

* **[배열형](/types/array)**: 기본 데이터형들을 순서대로 연결한 데이터

## 함수

* **[함수](types/function)**: 프로그램 내에서 편리하게 재사용 할 수 있도록 만든 코드 

## #custom

## 사용자 데이터

타입스크립트언어에서는 사용자-정의형 데이터 클래스를 만들 수 있습니다.

```typescript
class Foo {
    public bar: number;
    baz() {

    }
}
```