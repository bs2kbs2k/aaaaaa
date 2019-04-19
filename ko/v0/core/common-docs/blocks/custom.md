# 사용자 정의 블록

This page provides a short introduction to defining your own blocks in PXT.

## 사용자 정의 블록이란? 편집기에서 찾을 수 없습니다!

That's right. It's possible to define your own functions in JavaScript and turn them into blocks with the addition of some special comment macros.

Any exported JavaScript function can be turned into a block by simply adding a `//% block` comment:

```typescript
namespace fun {
    /**
    * 유명한 피보나치 수를 계산합니다!
    */
    //% block
    export function fib(value: number): number {
        return value <= 1 ? value : fib(value - 1) + fib(value - 2);
    }
}
```

There are several options to control the appearance of your blocks. We generate a few of those in the template to get you started. For the complete guide, read https://makecode.com/defining-blocks.

## 프로젝트 안에 블록 저장하기

`main.ts` 에 새로운 블록을 직접 추가하지 마세요. 회색 비활성 블록으로 나타나게 됩니다. Instead, follow the steps below to add a new file, `custom.ts`, and add all your blocks in that file.

In order to add `custom.ts` to your project, you do this:

* go to JavaScript
* **탐색기** 보기를 누른 후, 화면을 펼칩니다.
* 바로 나타나는 `+` 버튼을 누릅니다.
* accept the dialog to add a `custom.ts` file in your project

프로젝트에 파일이 이미 추가되어있다면, **탐색기** 보기를 이용해 간단히 살펴볼 수 있습니다.

## **패키지 추가하기...**에서 공유 프로젝트 사용하기

You can add a shared project as a dependent package and re-use all the blocks from that project. Just click on the **Extensions** button, paste the shared project url, and search.

## 개발 내용 적용 주기

Once `custom.ts` is added to your project, you can alternate between this file and the blocks view. The blocks will automatically reload on each iteration.

카테고리에 아무것도 나타나지 않는다면, 함수를 정의할 때 문법적 오류가 발생한 것일 수 있습니다. 프로그램 코드가 정상적으로 컴파일 되는지 확인하고, 컴파일 과정에서 출력된 메시지들이 정상인지 확인해보세요.

## 만든 블록 공유하기

직접 만든 블록들을 공유하는 가장 쉬운 방법은, [공유 버튼](/share)을 이용해 프로젝트 전체를 공유하는 것입니다.

## GitHub 로 가져가기

만든 블록들을 나중에 다시 재사용하려면, [패키지](/packages)로 변환시키는 방법도 생각해 볼 수 있습니다.