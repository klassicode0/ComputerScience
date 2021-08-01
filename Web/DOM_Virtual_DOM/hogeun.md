# DOM vs Virtual DOM

<br>

![DOM과 Virtual DOM](hogeun.assets/img.png)

> Virtual DOM은 렌더링 횟수를 최소화하여 효율성을 높입니다. (이미지 출처 : https://programmingwithmosh.com/react/react-virtual-dom-explained/)

<br>

DOM과 가상 DOM은 모두 브라우저에 표시되는 Document와 관련된 객체입니다.

<br>

Document는 HTML 문서를 의미합니다. HTML은 객체와는 거리가 먼 언어입니다. 그리고 이를 동적으로 만들어주는 JavaScript는 객체지향적인 언어입니다. 따라서 **개발자가 코드로 Document를 수정하기 위해 등장한 개념이 DOM(Document Object Model)입니다.** HTML 태그 엘리먼트들이 트리형태의 객체 모델로 구현되어 JavaScript와 연동가능하게 됩니다.

<br>

**최근에는 SPA의 등장으로 한 Document에서 동적인 새로고침이 빈번하게 발생합니다.** 매 새로고침 마다 DOM이 수정되는데 DOM의 수정은 렌더링이라는 비싼 작업을 동반합니다. 하나의 새로고침으로 10개의 DOM 요소에서 수정이 생기면 10번의 렌더링이 발생합니다.

<br>

가상 DOM은 렌더링 횟수를 최소화하기 위해 도입된 개념으로 JS로 Document를 수정할 때 바로 DOM을 수정하는 것이 아니라, DOM의 JS 객체 복제본인 가상 DOM을 먼저 수정하고 수정이 완료된 다음 기존의 가상 DOM과 수정된 가상 DOM 사이를 비교하며, 최종 수정된 내용만 DOM에 반영해 **렌더링 횟수를 최소화**할 수 있습니다.

<br>

**React.js나 Vue.js** 등 프론트엔드 프레임워크는 대부분 가상 DOM을 사용하고 있습니다.

<br><br>

Fin.

