# If

### @parent blocks/language

조건식의 계산(평가) 결과인 [불](/blocks/logic/boolean)의 참(true), 거짓(false) 값에 따라 선택적으로 코드를 실행합니다.

```blocks
if(true) {
}
```

(위에 있는) 어두운 파랑색 톱니바퀴 아이콘을 눌러, 현재 블록에 *아니면(else)* 이나 *만약(if)* 블록을 추가할 수 있습니다.

### 예시: 스크린 밝기 조정

```blocks
if(input.lightLevel()<100){
    led.setBrightness(255);
}
```

If the [light level](/reference/input/light-level) is `< 100`, this code sets the brightness to `255`:

### 참고 항목

[while loop](/blocks/loops/while), [for](/blocks/loops/for), [boolean](/blocks/logic/boolean)