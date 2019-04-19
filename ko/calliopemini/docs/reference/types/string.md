# 문자열

a piece of text.

### @parent blocks/language

A *String* is a sequence of characters. @boardname@ 에서는 ASCII 문자코드 32 에서 126 까지 지원됩니다.; 문자, 숫자, 문장 부호, 몇 가지 기호. a 로 출력되는 모든 문자 코드는? [LED 스크린](/device/screen) 에서.

### Create a string variable

```block
let salutation = "Hello";
```

문자열을 저장 변수를 만들기 위해서는:

1. Click `Variables` (in the Block drawer).

2. Type a name for your new string variable by clicking the down arrow, then click New Variable. Then type the variable name "salutation"

3. Drag a string block on the right side of the operator.

4. Click `"Hello"` and then type a string like `hello`.

작성한 코드는 아래와 같습니다.:

```block
let salutation = "Hello";
```

### The function `show string`

Use [show string](/reference/basic/show-string) to display a string on the [LED screen](/device/screen). If the string is multiple characters, the string scrolls right to left. The following example displays `Hello world!` on the @boardname@ screen:

```block
basic.showString("Hello world!");
```

The parameter of `show string` specifies the string

### 참고 항목

[string functions](/reference/types/string-functions), [Number](/reference/types/number), [show string](/reference/basic/show-string)