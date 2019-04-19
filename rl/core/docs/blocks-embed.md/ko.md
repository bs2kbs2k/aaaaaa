# Blocks embedding

MakeCode provides a lightweight blocks rendering engine that renders code snippets as SVG images.

## 스크린샷의 저주

Unlike text based programming languages, block-based snippets aren't easily rendered in a documentation page. 간단한 방법은 블록 코드 부분들 대한 스크린샷을 만드는 것인데, 내용이 자주 바뀔 수 있습니다.

* screenshots can't be compiled - so it's hard to maintain them
* 스크린샷은 다국어가 지원되지 않습니다. - 영어 사용자들이 아닌 경우 블록들을 읽을 수 없게 됩니다.
* screenshots aren't easily reloaded into the editor
* screenshots don't play well with source control systems - you cannot diff changes efficiently

## 원하는 위치에서 블록 렌더링하기

The MakeCode approach in solving this problem is to render the **JavaScript** code snippets on a client using the same block rendering engine as the editor. Under the hood, an IFrame from the MakeCode editor will render the blocks for you.

## Plugins

Here are some sample integrations for various documentation/blogging engines.

* [GitBook plugin](https://plugins.gitbook.com/plugin/pxt)
* [MkDocs plugin](https://microsoft.github.io/pxt-mkdocs-sample/)

## Manual Implementation

You can find example of custom blocks embedding in the documentation of your favorite editor.