# 길이

텍스트 문자열에 포함되어 있는 문자의 갯수를 알아냅니다.

```block
let text = "";
text.length;
```

## 리턴값

* 텍스트 문자열에 포함되어있는 문자의 [수(정수)](/types/number).

## 예시

문자의 개수가 100개 미만인 동안, 어떤 텍스트를 문자열에 계속 연결시켜 길이를 늘려갑니다.

```blocks
let tooShort = "";
while (tooShort.length < 100)
{
    tooShort = tooShort + "add some more...";
}
```