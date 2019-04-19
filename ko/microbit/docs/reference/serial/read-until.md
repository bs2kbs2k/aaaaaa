# 시리얼통신 문자까지 읽기

시리얼통신 포트로 전송된 문자열을, 구분 문자 위치까지 잘라 읽어옵니다.

```sig
serial.readUntil(",");
```

## 리턴값

* [문자열](/types/string). 시리얼통신 포트로 전송된 데이터를 포함하고 있는 문자열. 사용자가 입력해 전송시킨 문자열과 같은 문자열.

## 예시

다음 코드에서는 구분 문자(`,`)를 기준으로 문자열을 잘라 읽는 예시입니다.

```blocks
basic.forever(() => {
    let answer = serial.readUntil(",");
    serial.writeLine(answer);
});
```

## 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 값 전송](/reference/serial/write-value)