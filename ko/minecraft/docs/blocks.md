# @extends

## #blocksbase

Blocks snap into each other to make up the program that your @boardname@ will run. Blocks are events (**on command**, **on died**, ...) or other code that is snapped inside event blocks in order to run.

Event blocks (and the code inside them) are run when the events registered for them occur.

Code that you want to run just once when the program starts goes into the special [`||loops:on start||`](/blocks/on-start) event block. This block always runs first.

```namespaces
for (let i = 0;i<=5;++i) {}
if (true){}
let x = 0;
x = Math.randomRange(0, 5)
Math.randomRange(0, 5);
```