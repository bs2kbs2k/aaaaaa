# 사용자 정의 블록

This page provides a short introduction to defining your own blocks in MakeCode.

## Custom blocks? I can't find it in the editor!

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

Do not add block definitions directly into `main.ts` as they will show up as grey blocks. Instead, follow the steps below to add a new file, `custom.ts`, and add all your blocks in that file.

In order to add `custom.ts` to your project, you do this:

* go to JavaScript
* click on the **Explorer** view and expand it
* click on the `+` button that just appeared
* accept the dialog to add a `custom.ts` file in your project

If you already have added this file to your project, simply navigate to it using the **Explorer** view.

## Using a shared project in **Extensions**

You can add a shared project as a dependent extension and re-use all the blocks from that project. Just click on the **Extensions** button, paste the shared project url, and search.

## 개발 내용 적용 주기

Once `custom.ts` is added to your project, you can alternate between this file and the blocks view. The blocks will automatically reload on each iteration.

카테고리에 아무것도 나타나지 않는다면, 함수를 정의할 때 문법적 오류가 발생한 것일 수 있습니다. 프로그램 코드가 정상적으로 컴파일 되는지 확인하고, 컴파일 과정에서 출력된 메시지들이 정상인지 확인해보세요.

## 만든 블록 공유하기

The easiest way to share your blocks is to share the entire project using the [share button](/share).

## Taking it to GitHub

If you plan to reuse those blocks further, you might consider turning them into an [extension](/extensions).