# 블록 프로그래밍언어

### @description 블록 편집기를 위해 언어를 구성합니다.

## #blocksbase

Blocks snap into each other to define the program that your @boardname@ will run. Blocks can be event (buttons, shake, ...) or need to be snapped into an event to run. [시작하면 실행](/blocks/on-start) 블록이 가장 처음 실행됩니다.

## 블록

```namespaces
for (let i = 0;i<5;++i) {}
if (true){}
let x = 0;
```

## 내장 객체 #builtins

```namespaces
Math.randomRange(0,5);
"".compare("");
[0].push(0);
```

## 참고 항목

[논리](/blocks/logic), [반복](/blocks/loops), [변수](/blocks/variables), [계산](/reference/math), [문자열](/reference/text), [배열](/reference/arrays)

[on-start](/blocks/on-start), [javascript blocks](/blocks/javascript-blocks), [custom blocks](blocks/custom)