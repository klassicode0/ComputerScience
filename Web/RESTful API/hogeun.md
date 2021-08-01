# RESTful API

<br>

> 목차
>
> [REST, REspresentational State Trasfer](#rest-respresentational-state-trasfer)
>
> [REST의 특징](#rest의-특징)
>
> [RESTful API는 무엇인가](#restful-api는-무엇인가)
>
> [RESTful API의 구성 요소](#restful-api의-구성-요소)
>
> [RESTful API 설계 가이드 및 주의점](#restful-api-설계-가이드-및-주의점)
>
> [World Wide Web](#월드-와이드-웹-world-wide-web)
>
> [Hypermedia](#하이퍼미디어-hypermedia)
>
> [URI, URL, URN](#uri-url-urn)

<br>

![RESTful API 이란](hogeun.assets/restapi-image.png)

### REST, REspresentational State Trasfer

REST는 비교적 최근인 2000년에 Roy Fielding의(HTTP 주요 저자 중 한명) 박사학위 논문을 통해 소개된 Server-Client 통신 방법 중 하나이다. 위키백과의 정의는 다음과 같다. ***REST는 월드 와이드 웹과 같은 분산 하이퍼미디어 시스템을 위한 소프트웨어 아키텍처의 한 형식이다.*** "월드 와이드 웹과 같은 분산 하이퍼미디어 시스템을 위함"은 웹의 기존 기술과 HTTP 프로토콜을 그대로 사용하여 여러 링크에서 동시적으로 일어나는 네트워크 통신에 적합하기 때문이고, "소프트웨어 아키텍처의 한 형태"라고 말하는 까닭은 그 자체로 소프트웨어 작성에 대한 제한이자 가이드의 모음이기 때문이다.

<br>

### REST의 특징

1. ***인터페이스 일관성, Uniform Interface***
   * 자원에 접근할 수 있는 유일한 인터페이스는 URI와 HTTP 메소드를 사용하는 인터페이스이다.
2. ***클라이언트/서버, Client-Server***
   * 자원을 요청하는 Client와 자원을 제공하는 Server로 서로 구분되며 독립적이다.
   * 클라이언트는 UI, 사용자 인증, 세션 등을 관리한다.
   * 서버는 데이터 접근, 트래픽 관리, 보안 등을 관리한다.
3. ***무상태성, Stateless***
   * HTTP 프로토콜을 사용하기 때문에 REST 역시 무상태성을 갖는다.
   * 클라이언트는 context를 서버에 저장하지 않고, 서버는 각 요청을 별개의 요청으로 처리한다.
   * 이를 통해 서버의 자유도가 높아지고, 한대의 서버로도 다수의 클라이언트와 통신할 수 있다.
4. ***캐시 처리 가능, Cachable***
   * 서버는 캐싱이 불가능하다고 명시하지 않은 모든 리소스의 캐싱을 허용해야 한다.
   * 캐싱은 클라이언트 측에서 처리한다.
5. ***계층형 구조, Layered System***
   * 서버는 비즈니스 로직이나 보안, 로드밸런싱, 암호화, 사용자 인증 등 서로 다른 기능을 계층화할 수 있다.
   * 계층화된 구조는 서버의 구조적 유연성을 제공한다.
6. (Optional) ***Code on demand***
   * 서버가 클라이언트에 코드 스크립트 일부를 전달해 클라이언트에서 실행한다.

<br>

![img](hogeun.assets/restapi.png)

### RESTful API는 무엇인가

RESTful API, 편히 말해 REST API는 ***REST의 원칙을 따르는 API라는*** 뜻이다. API는 서버 관리자가 직접 사용하기도 하지만 대개 제3자에게 오픈하는 경우가 많다. 이 경우에 직접적인 서버 자원 접근은 차단하고, API를 통한 접근만을 허용하는데, 이를 통해 시스템의 안정성과 보안성을 높일 수 있다. 이때 제3자가 API를 잘 사용하기 위해서는 익숙한 형태가 좋을 것이다. 그렇기 때문에 일반적으로 REST API의 구현 목적은 ***HTTP와 동일한 일관된 컨벤션을 통해 API의 이해도와 호환성을 높이는*** 것이 주 목적이다.

<br>

RESTful API는 앞서 말했듯 HTTP를 사용하기 때문에 플랫폼 의존성이 적고, 기존의 웹 인프라를 그대로 사용할 수 있다는 큰 장점이 있다. 덕분에 범용적 인터페이스를 갖춘 Open API로 사용되기 적합하고, 유지보수가 용이하며 규모 확장성도 좋다.

<br>

다만 통신 프로토콜이 HTTP로 정해져있다는 점, 사용할 수 있는 메소드가 4개뿐이라는 점과 분산환경에 적합하지 않다는 점이 단점으로 뽑힌다.

<br>

### RESTful API의 구성 요소

REST API는 다음의 세가지로 구성된다.

1. 자원, resource
   * 자원은 서버에 존재하고 ***모든 자원에는 고유한 URI가 존재한다.***
   * Client는 URI를 이용해 자원에 접근할 수 있다.
2. 행위, verb
   * Client는 ***POST, GET, PUT, DELETE의 네가지 HTTP 메소드를 지원해 CRUD한다.***
3. 표현, representations
   * Client의 요청에 대해 Server는 응답을(representation) 보낸다.
   * 일반적으로 JSON 혹은 XML로 데이터를 주고 받으며, 응답의 가능한 데이터 포맷은 아래와 같다.
     * ***application/json***
     * ***application/xml***
     * application/x-wbe+xml
     * application/x-www-form-urlencoded
     * ***multipart/form-data (멀티미디어 파일)***

<br>

### RESTful API 설계 가이드 및 주의점

1. 자원과 행위의 올바른 구분
   * 모든 요청이 자원의 URL로 구성되기 때문에 URL 이름을 신경써야 한다.
   * 각 메소드는 목적에 맞는 메소드를 사용해야 한다.
2. 표현 메시지에서 header와 body의 올바른 구분
   * body는 Entity를, header는 이외에 API 버전 정보, MIME 타입 등 컨트롤 정보들을 포함한다.
3. Self-descriptiveness, 자기표현적 메시지
   * URL이나 메소드 뿐 아니라 header를 포함한 메시지의 모든 내용에 대한 충분한 정보가 포함되어야 한다.
   * 메시지만으로도 쉽게 이해될 수 있어야 한다.
4. 주의 깊은 API 버전 관리
   * 하위호환성을 고려한 버전 관리를 해야 한다.
5. 보안 관리
   * HTTPS, 수상한 도메인으로부터의 접근 차단 등 보안을 신경써야 한다.
6. 올바른 에러 코드와 메시지
   * HTTP 에러 코드 표준에 맞는 올바른 에러 코드와 메시지를 리턴할 수 있어야 한다.

<br>

> #### 월드 와이드 웹, World Wide Web
>
> 그냥 웹으로도 불리는 월드 와이드 웹은 인터넷 상에 다양한 정보를 검색할 수 있게 해주는 정보검색 시스템이다. 인터넷 자체와 혼동되는 경우가 있지만, 이 둘은 다른 것이며, 월드 와이드 웹은 인터넷에 포함되는 하나의 서비스로 이해되어야 한다. 인터넷에 산재된 여러 자원 사이를 오가도록 만드는 WWW의 가장 핵심 기능 세가지는 ***1) URL과 같은 웹 자원의 위치 지정 방법, 2) HTTP와 같은 자원에 접근하기 위해 따라야하는 프로토콜, 3) 그리고 하이퍼미디어를 표현하는 HTML이다.*** 이외에도 [여러 기능](https://en.wikipedia.org/wiki/World_Wide_Web#Function)이 있다.

<br>

> #### 하이퍼미디어, Hypermedia
>
> 유사한 단어인 Hypertext, Hyperlink와 공유하는 Hyper-라는 접두사에서 알수 있듯이 하이퍼미디어도 ***비선형적인 참조 연결을*** 포함한다. 다만, 참조되는 대상이 일반 텍스트 뿐 아니라 그래픽, 음성, 영상 등 ***multimedia를 포함한다는*** 점에서 Hypertext보다 확장된 개념이다. 현대의 월드 와이드 웹이 대표적인 예시이다.
>
> ![img](https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/Sistema_hipertextual.jpg/220px-Sistema_hipertextual.jpg)

<br>

> #### URI, URL, URN
>
> URI, uniform resource identifier는 특정 자원을 한정할 수 있는 식별자를 의미하며, URL과 URN을 포함하는 상위 개념이다. 현재까지는 URN의 사용이 많지 않기 때문에 보통 URI를 말하면 URL을 의미하기도 한다.
>
> URL, uniform resource locator는 해당 자원에 접근하기 위한 프로토콜을 포함하는 특별한 식별자를 의미한다. 프로토콜에는 HTTP, HTTPS, FTP 등이 있다.
>
> URN, uniform resource name은 해당 자원이 지니는 고유한 이름으로 사람의 주민등록번호와 비슷하다. 위치와 상관없이 지칭할 수 있다는 장점이 있다. 도서마다 부여되는 ISBN 코드가 대표적인 예시이다.
>
> ![url uri url miessler 2020](https://danielmiessler.com/images/url-uri-url-miessler-2020.png)

<br><br>

> 출처 목록
>
> * [Wikipedia - World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web)
> * [Wikipedia - Hypermedia](https://en.wikipedia.org/wiki/Hypermedia)
> * [위키백과 - REST](https://ko.wikipedia.org/wiki/REST)
> * [Daniel Miessler - What’s the Difference Between a URI and a URL?](https://danielmiessler.com/study/difference-between-uri-url/)
> * [NHN Cloud - REST API 제대로 알고 사용하기](https://meetup.toast.com/posts/92)
> * [GitHub - JaeYeopHan/Interview_Question_for_Beginner](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Development_common_sense#restful-api)
> * [TechTarget - REST API (RESTful API)](https://searchapparchitecture.techtarget.com/definition/RESTful-API#:~:text=A%20RESTful%20API%20is%20an,deleting%20of%20operations%20concerning%20resources.)
> * [Heee's Development Blog - [Network] REST란? REST API란? RESTful이란?](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)

<br><br>

Fin.

