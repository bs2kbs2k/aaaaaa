# 프로젝트 공유하기

프로젝트를 만들고 나면, 클라우드에 저장시키거나, 공유하거나, 다른 웹사이트에 내장시킬 수 있습니다.

* **더 보기...** 를 누른 후 **프로젝트 내장시키기**를 누르세요.:
* **프로젝트 배포하기** 를 누릅니다. 이렇게 하면 프로젝트를 공개적으로 공유할 수 있게 됩니다.
* 프로젝트를 공유시키게 되면, 다음과 같은 정보들을 볼 수 있습니다.:

## URL 주소 공유하기

다른 사람들을 위해 프로젝트의 URL 주소를 공유할 수 있으며, 그렇게 공유가 되면 다른 사람들이 프로젝트를 보고, 다운로드하고, 편집할 수 있게 됩니다.

### ~hint

**개발자:** 이 페이지는 [OEmbed](https://oembed.com/) 기능을 지원합니다.

### ~

## 블로그나 웹사이트에 내장시키기

단순히 링크를 공유하는 것보다, 프로젝트를 내장시켜, 여러분의 웹사이트를 방문한 사람들이 시뮬레이터를 사용하고, 블록이나 코드를 편집하고, 프로젝트를 다운로드 할 수 있도록 만들 수 있습니다.

### 일반적인 방법

내장 시킬 방법을 선택합니다.

* **스크린샷** - 블록 조각으로 링크되는 간단한 스크린샷
* **편집기** - 최소한의 인터페이스와 함께 내장된 편집기
* **시뮬레이터** - 시뮬레이터만 내장
* **명령어 입력창** - [명령어 입력](/cli) 도구를 사용해 압축된 프로젝트를 해제하는 특별한 명령어들

프로젝트 게시 대화상자에서, 임베드시킬 HTML 코드를 복사하세요. 다음과 같이 나타나게 될 것입니다.:

블로그나 웹사이트의 HTML 편집기를 열고, HTML 코드를 원하는 위치에 복사해 넣으세요.

### 워드프레스(Wordpress)

[wordpress.com](https://wordpress.com) 의 블로그들은 대부분의 웹 사이트에 대한 내장형 코드들을 지원하지 않습니다. 따라서, 프로젝트 링크를 사용해야합니다. 다른 방법으로, Wordpress VIP 계정을 가지고 있는 경우에는 [이 방법](https://vip.wordpress.com/documentation/embedding-rich-media-from-around-the-web-with-protected-embeds/#scripts-iframes-and-objects) 을 사용해 `iframe` 을 여러분의 블로그에 내장시킬 수 있습니다. 추가하고 싶은 URL 주소를 `@homeurl@/#pub:PROJECTID` 와 같이 작성해야합니다. `PROJECTID` 는 프로젝트의 고유한 식별자로 바꿔야 합니다.

Wordpress 기반의 블로그 서버를 운영하고 있다면, [iframe-plugin](https://wordpress.org/plugins/iframe/) 을 설치한 후, 다음과 같은 코드를 블로그 글에 작성합니다.(마찬가지로, `PROJECTID` 를 프로젝트의 고유한 식별자로 바꾸어야 합니다.):

    [iframe src="@projectid@/#pub:PROJECTID"]
    

### 블로거(Blogger)

* 새 게시물을 만듭니다.
* 'Compose' 옆에 있는 'HTML' 버튼을 눌러, HTML 코드를 붙여넣습니다.

### 스퀘어스페이스(Squarespace)

[Squarespace](https://squarespace.com) 에서는 블로그 포스트나 페이지에 내장형 HTML 코드를 사용할 수 있습니다. 편집기에서, 새로운 블록을 추가하려면 누르세요.

아래로 스크롤하여 **More** 를 찾은 후, **Code** 를 선택합니다. 내장형 HTML 코드를 붙여넣은 후, **Apply** 를 클릭합니다.

### 구글 사이트(Google Sites)

Google Sites 는 현재 [HTML 안에 있는 iframes](https://support.google.com/sites/answer/2500646?hl=en) 이 지원되지 않습니다. 따라서, 프로젝트의 URL 주소 대신 링크를 삽입해야 합니다.

### 오피스 스웨이(Office Sway)

[Microsoft Office Sway](https://sway.com/my) 는 [특정 웹사이트](https://support.office.com/en-us/article/Embed-content-in-your-Sway-1e1ab12a-f961-4a26-8afc-77a15f892b1d) 에서만 iframes 를 허용합니다. 따라서, 프로젝트 대신 링크를 삽입해야 합니다.

### 마크다운 문서 내장(Embedding in Markdown documents)

[Markdown](https://daringfireball.net/projects/markdown/) 은 많은 블로그 편집기에서 지원되는 유명한 텍스트 포맷입니다. Markdown 에서 내장형 HTML 코드를 지원하는 경우, HTML 코드를 문서에 삽입할 수 있습니다. 하지만, 허용되지 않는 사이트들도 있습니다.