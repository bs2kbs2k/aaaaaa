# 블루투스에 대하여

![](/static/bluetooth/Bluetooth_SIG.png)

## 소개

블루투스는 라우터나 액세스 포인트와 같은 중앙 장치없이, 장치들끼리 서로 통신 할 수 있도록하는 무선 통신 기술입니다.

블루투스는 특별한 "저 에너지 기능" 사용할 수 있습니다. 저 에너지 기능을 사용하는 장치는 큰 전력을 필요로하지 않습니다. @boardname@ 는 블루투스 저 에너지 기능을 사용합니다.

블루투스 저 에너지 세계에서는, 다른 장치와 통신할 수 있도록 하는 방법을 정의한 "프로파일"을 가지고 있습니다. 블루투스 프로파일은, 어떤 장치에 나타나는 다른 장치들을 그 특징과 기능 관점에서 분류해서 정의하는 방법이라고 할 수 있습니다.

다른 관점에서 보면, 블루투스 프로파일은 실제로 인터페이스 상세사양이라고 할 수 있습니다. 어떤 장치가 가지고 있는 데이터를 정의하는데, 다른 장치들이 블루투스 연결을 통해서 주고 받을 수 있는지와, 연결된 장치가 어떻게 반응해야 하는지를 포함하고 있습니다. 자 이제 기술적인 세부사항을 좀 더 자세하게 살펴보도록 하겠습니다.

## 기본 개념

블루투스 장치는 다양한 방법으로 다른 연결된 장치에 액세스 할 수 있는 속성 테이블이라는 데이터 테이블을 가지고 있습니다. 데이터와 그 데이터들을 다루는 방법들이 포함되어있는 테이블에 대한 내용은, Generic Attribute profile 또는 "GATT" 라고 부르는 블루투스에 대한 기술적인 내용입니다. GATT 용어에 대한 내용들은 안드로이드 플랫폼 등에서 제공하는 API 에 대한 문서자료 등에서 살펴볼 수 있습니다.

속성 테이블은 여러 가지 데이터들로 구성된 레코드들과 비슷한 정보들을 포함하고 있습니다. 주 데이터 타입은 Services, Characteristics, Descriptors 라고 부르는 것들입니다. 이러한 용어들에 대해서 순서대로 살펴보도록 하겠습니다.

## Attributes

Services, Characteristics, Descriptors 는 속성을 나타내는 데이터 타입입니다. 따라서, Generic Attribute Profile 과 Attribute Table 등은 속성 프로토콜이라고도 부릅니다. 모든 속성들은 UUID (Universally Unique Identifier) 에 의해 구별되는 데이터 타입을 가지고 있습니다. 몇 몇 속성들은 Bluetooth SIG 에 의해서 정의되며, 블루투스를 위한 기술 표준과 함께 16 비트 길이의 UUID 들을 가지고 있습니다. 일부 속성들은 제조사의 제품 팀에 의해 특정 장치를 위해 설계된 것으로, 128 비트의 UUID 들을 가지고 있습니다. @boardname@ 는 16 비트와 128 비트 UUID 를 함께 결합해 사용합니다.

## Structure

Services, Characteristics, Descriptors 들은, 가장 상위에 Services 가 위치하고 가장 아래쪽에는 Descriptors 가 있는 계층 구조로 구성됩니다. Services 는 한 개 이상의 Characteristics 를 포함합니다. Characteristic 에는 0 개 이상의 Descriptor 들이 포함됩니다. Descriptors 는 완전히 옵션이기 때문에 0 이 가능하지만, Service 는 적어도 한 개 이상의 Characteristic 을 포함해야 합니다.

![](/static/bluetooth/gatt_hierarchy.png)

## Services

Service 는 논리적으로 연관되어있는 블루투스 데이터 항목들의 컨테이너입니다. 이러한 데이터 항목들을 실제로 Characteristics 라고 부릅니다. Service 는 Characteristics 들이 그 안에 포함되어있는 것이라고 생각할 수 있습니다. 어떤 Service 는 특별한 버튼이나 센서와 관련된 기능(예를 들어, 하드웨어적 기능)을 나타내기도 합니다. Bluetooth SIG 에 의해 정의된 Service 의 예는 장치 정보 서비스(Device Information Service)로서, 그 이름에서 알 수 있듯이, 제조사와 시리얼 번호 등과 같은 하드웨어 장치와 관련된 다양한 정보 항목들을 포함하고 있습니다. @boardname@ 에도 이 서비스가 있습니다.

## Characteristics

Characteristics 는 특별한 내부 장치의 상태와 관련된 항목들로서, 그 장치가 센서를 이용해 측정할 수 있는 주변 환경 상태 등과 같은 정보들을 포함할 수 있습니다. 현재 배터리 충전 상태는 내부 상태와 관련된 예이고, 주변 온도는 센서에 의해 측정될 수 있는 상태라고 할 수 있습니다. Characteristics 는 때때로 측정하고자하는 주파수와 같은 설정 데이터를 나타내는 경우도 있습니다. 이러한 모든 경우에서, 다른 블루투스 장치로 그러한 데이터들을 전달하기 위해서는 Characteristic 를 사용 가능하게 함으로서 가능합니다. Bluetooth SIG 에 의해서 정의된 Characteristic 의 예시 중 하나는 시리얼 번호 문자열로서, Device Information 서비스 내부에서 찾을 수 있습니다.

Characteristics 여러 개의 부분을 포함하고 있습니다. 각 파트들은 데이터형(type), 값(value), 속성(properties), 권한(permissions) 을 가지고 있습니다.

데이터형(Type)은 이전에 이미 설명되었고, UUID 값은 특정 타입의 Characteristic 를 나타내는 Attribute 입니다. Value 는 관련된 상태 데이터의 값입니다.

속성은 다른 장치가 블루투스를 통해 할 수 있는 특성 characteristic 을 정의합니다. READ, WRITE, NOTIFY 과 같은 다양한 동작들이 정의되어있습니다. 어떤 characteristic 을 읽는다는 것은, 속성 테이블에 나타나있는 현재 값을 블루투스를 통해 연결된 장치에 전송한다는 것을 의미합니다. 쓰기는 연결된 장치의 상태 테이블에 있는 값을 변화시키는 것을 의미합니다. Notifications 알림은 특별한 메시지 타입으로, @boardname@ 와 같은 장치가 연결된 블루투스 장치에 전송되는 데이터이며, 관련된 characteristic 값이나 타이머에 의해 주기적으로 제어되는 변화 값을 전송할 수 있습니다. 모든 Characteristics 가 모든 동작에 적용되는 것은 아닙니다. Characteristic 의 속성들은 어떤 동작들이 지원되는지 알 수 있도록 해줍니다.

속성 테이블에 있는 어떤 값을 읽거나 쓰는 동작과 같은 프로세스가 일어나는 특별한 과정에서 동작하도록, 어떤 장치에 프로그래밍 할 수 있습니다. 따라서, 연결된 상태에서 데이터를 간단히 전송하는 것보다 더 많은 작업들이 수행되도록 할 수 있습니다. 예를 들어, Characteristic 값을 변화시키는 것은, 해당 장치의 가속도 센서 값을 읽어들이는 주기를 변화시키는 것과 같은 효과를 만들어 낼 수도 있습니다.

Permissions 는 보안과 관련된 것으로, 보안 조건들을 상세하게 기술함으로써, 어떤 characteristic 를 읽거나 쓰려고 접근할 때, 가능 여부를 판별할 수 있도록 해줍니다.

## Descriptors

Descriptors 는 Descriptor 에 포함되어있는 Characteristic 과 관련된 상세사항과 관련된 메타 데이터를 포함하고 있기 때문에, Characteristic 와 관련된 동작들을 조절할 수 있습니다. 예를 들어, Client Characteristic Configuration Descriptor 라고 부르는 특별한 descriptor 를 사용해 알림 메시지를 활성화시키거나 해제할 수 있습니다.

## Profile

블루투스 프로파일은, 블루투스 장치의 동작과 관련해서 필요한 모든 정보들이 함께 묶여있는 상세사항이라고 할 수 있습니다. 서비스 접근 방법, characteristics 와 descriptors, 보안 규칙, 동시 실행 제한 사항 등.

## Client Server Architecture

스마트폰 프로그램이 블루투스를 통해 @boardname@ 와 같은 장치들과 연동되어 동작할 때, client/server 연결 구조가 됩니다. 스마트폰 앱은 GATT client 가 되고, @boardname@ 는 GATT server 로서 역할을 하게 됩니다. Attribute(ATT) 프로토콜이라고 부르는 프로토콜을 사용해 서로 통신하게 됩니다. 스마트폰 앱 개발자로서 API 들을 다루어 본 사람들이라면, ATT 프로토콜 데이터들과 같은 것들을, 규격에 맞추어 만들어내는 것에 대해서 걱정할 필요가 없습니다.

![](/static/bluetooth/services_and_GATT.png)

## Device Discovery

어떤 블루투스 장치들과 관련해서, 이상의 내용들에서 살펴본 모든 것들은 GATT 클라이언트/서버로서 연결되고, 서로 통신하게 됩니다. 하지만, 두 장치가 서로 연결되어있지 않는 상황이라면 그 전에 먼저 수행되어야 하는 단계가 있습니다. 어떻게 두 장치가 서로 찾고 연결될 수 있는 것일까요? 그 질문에 대한 대답은 'Device Discovery' 라는 용어에 있습니다. 그리고, Generic Access Profile (GAP) 라고 불리는 블루투스 구성 및 연결과 관련되어있습니다.

GAP 에서, 먼저 한 장치가 작은 패킷 데이터들을 주기적으로 주변에 발산(전송)시킵니다. 이 패킷들에는 신호를 발산(전송)하는 장치에 대한 정보가 포함되어있습니다. 다른 장치는, 자신에게 연결하는 장치를 찾는 스캐닝이라는 동작을 수행합니다. 발산(전송)된 패킷들을 수신해 처리하고, 관계가 없는 장치들로부터 나오는 신호들을 필터링해 걸러냅니다. 일반적으로 사용자에게는, 발견된 장치들에 대한 정보만 알려주고, 어떤 장치를 연결할 지를 선택하도록 합니다. 블루투스 신호를 발산(전송)한 장치를 블루투스 주변장치라고 부르고, 그러한 주변장치들을 스캔하는 장치는 블루투스 중앙 장치(Bluetooth Central device)라고 부릅니다. @boardname@ 는 블루투스 주변장치입니다.

@boardname@ 의 블루투스

@boardname@ 블루투스 기능에 사용된, 블루투스 프로파일에 관한 모든 참고 문서는, [Lancaster University documentation](http://lancaster-university.github.io/microbit-docs/ble/profile/) 웹사이트에서 찾아볼 수 있습니다.

@boardname@ 의 가속도(움직임 감지) 센서, 자기(디지털 나침반) 센서, 앞면 버튼 2 개, LED 디스플레이, 엣지 컨넥터 입출력 핀, 내부 메시지 버스, 내부 온도 센서 등 모든 것들에 대한 데이터들은 Service 로서 제공되기 때문에, 연결되는 블루투스 장치들은 이러한 기능들을 모두 사용할 수 있습니다. 추가:

* Bluetooth SIG 에 의해 정의된 Device Information Service 에는 응용프로그램들이 블루투스를 통해 펌웨어 버전과 같은 정보를 얻어낼 수 있도록 되어있습니다.
* Device Firmware Update (DFU) 서비스가 포함되어있기 때문에, 새로운 @boardname@ 코드를 USB 케이블 연결 없이 블루투스를 통해 업로드 할 수 있습니다.
* UART 서비스를 이용해, 일반적인 시리얼통신 방법과 유사한 방법으로 @boardname@ 와 자유로운 형태의 데이터를 교환할 수 있습니다.

@boardname@ 의 블루투스 기능을 통해 수행할 수 있는 모든 것은, 읽고 쓰고 알림 메시지를 보내는 동작들을 이용해 만들어낼 수 있습니다. 모든 characteristics 가 이상의 3 가지 방법을 통해 지원되지는 않습니다. 따라서, 프로파일 상세문서를 참고하시기 바랍니다. 때때로, 다른 동작들을 제어하는 설정 값을 쓰기 위한 목적의 Characteristics 가 있을 수 있습니다. 이러한 것을 전문적으로 컨트롤 포인트(Control Points)라고 합니다. 예를 들어, 가속도 센서값 측정 주기를 원하는 값으로 바꾸고 싶을 때, Notification 메시지로 프로그램에 전달될 수 있습니다.

## 더 자세히 알아보고 싶은가요?

일반적으로, Bluetooth SIG 웹페이지 http://www.bluetooth.com 에서 더 자세한 정보들을 찾아볼 수 있습니다. Bluetooth SIG 에 의해 정의된 프로파일, 서비스, characteristics, descriptors 들을 모두 찾아볼 수 있을 뿐만 아니라, 모든 블루투스 기술에 대한 핵심 상세 사항들도 찾아볼 수 있습니다.

자 이제 모든 설명이 끝났습니다. @boardname@ 의 블루투스 기능들을 즐겨보세요!

마틴 울레이(Martin Woolley), Bluetooth SIG. Twitter: @bluetooth_mdw

### 동영상

https://www.youtube.com/watch?v=aep_GVowKfs

## 참고 항목

[블루투스에 대하여](/reference/bluetooth/about-bluetooth), [@boardname@ 블루투스 프로파일 개요](http://lancaster-university.github.io/microbit-docs/ble/profile/), [@boardname@ 블루투스 프로파일 찾아보기](http://lancaster-university.github.io/microbit-docs/resources/bluetooth/microbit-profile-V1.9-Level-2.pdf), [@boardname@ 블루투스 자원](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html), [블루투스 SIG](https://www.bluetooth.com)

```package
bluetooth
```