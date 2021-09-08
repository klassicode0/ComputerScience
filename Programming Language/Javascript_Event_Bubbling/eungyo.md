# 자바스크립트에서 이벤트 버블링(Event Bubbling)이란 무엇인가요?

이벤트 버블링이란 한 요소에 이벤트가 발생하면 거품이 발생해서 위로 부풀어오르듯 이 요소에 할당된 핸들러가 동작하고, 이어서 부모 요소의 핸들러가 동작하는 현상입니다. 이 요소에 할당된 핸들러가 가장 최상단의 조상 요소를 만날 때까지 요소 각각에 할당된 핸들러가 동작합니다. 

```html
<form onclick="alert('form')">FORM
  <div onclick="alert('div')">DIV
    <p onclick="alert('p')">P</p>
  </div>
</form>
```

예제에서 가장 안쪽의 <p> 를 클릭하면 <p>에 할당된 onclick 핸들러가 동작 -> 바깥의 <div>에 할당된 onclick 핸들러가 동작 -> 그 바깥의 <form>에 할당된 onclick 핸들러가 동작하게 됩니다.