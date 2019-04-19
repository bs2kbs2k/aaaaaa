# Types

A *type* refers to a class of data and the operations permitted on that class of data. The following built-in types are supported for the @boardname@:

## 기초(기본) 데이터형 #primitives

* **[Number](/types/number)**: an integer number (32-bit signed)
* **[String](/types/string)**: a sequence of characters
* **[Boolean](/types/boolean)**: true or false

## 복합 데이터형 #complex

* **[배열형](/types/array)**: 기본 데이터형들을 순서대로 연결한 데이터

## 함수

* **[Function](types/function)**: code you can reuse anywhere in a program 

## #custom

## User data

TypeScript allows you to create user-defined classes of data.

```typescript
class Foo {
    public bar: number;
    baz() {

    }
}
```