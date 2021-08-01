# 브라우저에서 웹페이지가 구성되는 단계를 설명해보아라

<br>

### Lv 1 : 가장 간단한 설명

HTML이 웹페이지의 구조를 결정하고, CSS가 사용자 화면에 드러날 모양을 만들고, JavaScript가 사용자와 상호작용하는 요소를 결정 짓습니다.

<br><br>

### Lv 2 : 더 자세한 설명

#### Load HTML

먼저 웹 페이지를 구조적으로 나타내는 Markup 파일인 HTML이 로드됩니다.

<br>

#### Parse HTML

HTML Parser가 HTML 문서를 브라우저가 이해할 수 있는 DOM Tree, Document Object Model Tree 객체로 파싱한다.

<br>

#### Load CSS

(일반적으로 header에 style 태그가 포함되기 때문에) 다음으로 모양을 나타내는 Style 파일인 CSS가 로드됩니다.

<br>

#### Parse CSS

마찬가지로 CSS Parser가 CSS 파일을 해석해 CSSOM Tree, CSS Object Model Tree 객체로 파싱합니다.

> ![Parsing the HTML into a DOM tree](https://2r4s9p1yi1fa2jd7j43zph8r-wpengine.netdna-ssl.com/files/2017/08/05-01-500x349.png)
>
> Parse는 문자열 문서인 HTML을 구조화된 객체로 바꿔주는 과정입니다. (이미지 출처 : https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/)

<br>

#### Style

CSS 엔진은 각각의 DOM 노드들에 대해 어떤 CSS 규칙을 적용되어 있는지 확인하고, CSS 속성값들을 결정합니다. 이 과정이 끝나면 DOM과 CSSOM은 Render Tree로 결합된다.

> ![Styling each DOM node in the tree by attaching computed styles](https://2r4s9p1yi1fa2jd7j43zph8r-wpengine.netdna-ssl.com/files/2017/08/05-02-500x340.png)
>
> CSS 엔진이 각각의 DOM 노드들에 대해 알맞은 스타일을 실시합니다. (이미지 출처 : https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/)

> ![DOM 및 CSSOM은 결합되어 렌더링 트리를 생성합니다.](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/images/render-tree-construction.png)
>
> DOM과 CSSOM이 합쳐진 Render Tree는 대략 이런 모습입니다. (이미지 출처 : https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model)

<br>

#### Layout

브라우저는 Render Tree의 노드들을 Box로 취급해 화면의 어디에 얼마만한 사이즈로 배치할지 결정합니다.

> ![Measuring all of the boxes to create a frame tree](https://2r4s9p1yi1fa2jd7j43zph8r-wpengine.netdna-ssl.com/files/2017/08/05-3-500x371.png)
>
> 계층 구조에 따라 박스(노드) 속에 박스가 있을 수 있습니다. (이미지 출처 : https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/)

<br>

#### Paint

브라우저는 각 박스들에 스타일을 적용해 겉보기를 완성합니다. 각 박스를 칠하는 과정은 여러 레이어로 구분될 수 있습니다.

> ![Painting layers](https://2r4s9p1yi1fa2jd7j43zph8r-wpengine.netdna-ssl.com/files/2017/08/05-04-500x356.png)
>
> 마치 기름종이에 애니메이션을 그리듯 하나로 보이는 화면은 여러 레이어로 구성됩니다. (이미지 출처 : https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/)

<br>

#### Composite & Render

Paint가 완료된 레이어를 한 화면으로 합쳐 사용자가 볼 수 있는 브라우저 화면에 출력합니다.

> ![Assembling the layers together and taking a picture](https://2r4s9p1yi1fa2jd7j43zph8r-wpengine.netdna-ssl.com/files/2017/08/05-05-500x334.png)
>
> 렌더링의 과정은 사진을 찍는 것과 비슷합니다. (이미지 출처 : https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/)

<br>

#### Load JS & media files

화면에 포함되는 용량이 큰 파일이 (이미지, 영상 파일 등) 추가 로드되고, (일반적으로 body 태그의 마지막에 포함되는) JavaScript가 마지막으로 로드됩니다.

이 과정은 HTML, CSS Load보다 이후에 일어나지만 그렇다고 앞선 단계들과 완전한 순차 단계는 아니고, Parse 이후부터 비동기적으로 일어날 수 있습니다.

<br>

#### Interact with JS

JS가 작동함에 따라 사용자나 브라우저의 변화에 상호작용합니다.

<br><br>

### Lv 3 : DOM Parsing에 대한 더 자세한 설명

> ![DOM 트리](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/images/full-process.png)
>
> 이 그림은 파싱 과정에 따른 데이터의 모습을 보여줍니다. (이미지 출처 : https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model)

<br>

#### Conversion, 변환

브라우저가 HTML 파일에 명시된 인코딩에 (utf-8 등) 따라 HTML 파일을 문자열 데이터로 변환합니다.

<br>

#### Tokenizing, 토큰화

브라우저가 문자열을 W3C HTML5 표준에 지정된 고유 토큰으로 변환합니다.

<br>

#### Lexing, 렉싱

브라우저가 토큰을 객체(Node)로 변환한다. 노드에는 속성값들이 들어있습니다.

<br>

#### DOM Construction, DOM 생성

브라우저가 HTML 마크업 관계에 따라 각 노드를 트리 데이터 구조로 연결시킨다. 이로서 Parsing이 완료됩니다.

<br><br>

> 출처 목록
>
> * [**mozilla hack** - Inside a super fast CSS engine: Quantum CSS (aka Stylo)](https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/)
> * [**Google** - Web Fundamentals](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model)
> * [**webclub** - 브라우저의 역할과 스크립트의 로드 시점](https://webclub.tistory.com/630)

<br><br>

Fin.

