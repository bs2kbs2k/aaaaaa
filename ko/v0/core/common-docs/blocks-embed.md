# 블록 내장시키기

MakeCode 는 프로그램 크기가 작은 블록 렌더링 엔진을 제공하며, 블록 렌더링 엔진은 코드 조각을 SVG 이미지들로 변환시켜 보여줍니다.

## 스크린샷의 저주

텍스트 기반 프로그래밍 언어와 다르게, 블록 기반의 코드들은 문서 페이지에서 쉽게 렌더링 되지 않습니다. 간단한 방법은 블록 코드 부분들 대한 스크린샷을 만드는 것인데, 내용이 자주 바뀔 수 있습니다.

* 스크린샷은 컴파일되지 않습니다. - 그렇기 때문에 변하는 상황에 맞추어 유지시키는 것이 어렵습니다.
* 스크린샷은 다국어가 지원되지 않습니다. - 영어 사용자들이 아닌 경우 블록들을 읽을 수 없게 됩니다.
* 스크린샷은 편집기에서 쉽게 로드되지 않습니다.
* 스크린 샷은 소스 코드 제어 시스템에서 정상적으로 동작하지 않습니다. - 코드 변화에 따라 쉽게 변화시키지 못합니다.

더 나은 방법을 찾고 있다면, 다음 내용으로 계속 읽어가 주세요.

## 원하는 위치에서 블록 렌더링하기

MakeCode 는 이러한 문제를 해결하기 위해, 코드 조각을 웹 클라이언트 쪽에서서 렌더링할 수 있도록 하고 있습니다. 그렇게 하면, 편집기에서 보이는 것과 똑같이 블록을 사용할 수 있기 때문입니다. 그러기 위해서는 MakeCode 편집기로부터 iframe 을 로드시켜야 합니다.

## 구현

첫 번째로는, `IFrame` 렌더링 엔진과 연결시킬 수 있는 메시지 핸들러를 등록하는 것입니다. 렌더링 엔진 로드가 완료되고 메시지를 수신할 준비가 되면, `renderready` 메시지를 전송합니다.

```typescript-ignore
export interface RenderReadyResponseMessage extends SimulatorMessage {
    source: "makecode",
    type: "renderready"
}
```

렌더링 엔진은 렌더링된 블록들과 함께 `renderblocks` 응답 메시지를 보내옵니다.

```typescript-ignore
export interface RenderBlocksRequestMessage extends SimulatorMessage {
    type: "renderblocks",
    id: string;
    code: string;
    options?: {
        package?: string;
        snippetMode?: boolean;
    }
}

export interface RenderBlocksResponseMessage extends SimulatorMessage {
    source: "makecode",
    type: "renderblocks",
    id: string;
    svg?: string;
    width?: number;
    height?: number;
}
```

이 코드는 메시지 핸들러를 등록합니다. 원하는 JS 프레임워크를 사용해 작성하면 됩니다.

```typescript-ignore
window.addEventListener("message", function (ev) {
    var msg = ev.data;
    if (msg.source != "makecode") return;

    switch (msg.type) {
        case "renderready":
            // start rendering snippets!
            break;
        case "renderblocks":
            var svg = msg.svg; // this is an string containing SVG
            var id = msg.id; // this is the id you sent
            // replace text with svg
            var img = document.createElement("img");
            img.src = msg.uri;
            img.width = msg.width;
            img.height = msg.height;
            var code = document.getElementById(id)
            code.parentElement.insertBefore(img, code)
            code.parentElement.removeChild(code);
            break;
    }
}, false);
```

코드를 렌더링 하려면, 렌더링 IFrame 으로 `renderblocks` 메시지를 전송하면 됩니다.

```typescript-ignore
function makeCodeRenderPre(pre) {
    var f = document.getElementById("makecoderenderer");
    f.contentWindow.postMessage({
        type: "renderblocks",
        id: pre.id,
        code: pre.innerText
    }, "@homeurl@");
}
```

마지막 단계는, 렌더링 iFrame 을 HTML DOM 에 로드하고, 다른 코드들과 간섭하지 않도록 숨기면 됩니다.

```typescript-ignore
function makeCodeInjectRenderer() {
    var f = document.createElement("iframe");
    f.id = "makecoderenderer";
    f.style.position = "absolute";
    f.style.left = 0;
    f.style.bottom = 0;
    f.style.width = "1px";
    f.style.height = "1px";            
    f.src = "@homeurl@--docs?render=1"
    document.body.appendChild(f);
}

// load the renderer
makeCodeInjectRenderer();
```