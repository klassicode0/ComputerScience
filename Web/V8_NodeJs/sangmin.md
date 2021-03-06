# V8 엔진과 Node.js에 대해 아는만큼 설명해주세요

<br>

###  V8

V8은  웹 브라우저를 만드는 데 기반을 제공하는 오픈 소스 자바스크립트 엔진입니다.

<br>

V8 엔진의 구동 원리에 대해서 간략하게 말씀드리겠습니다.

<br>

`V8`은 작성된 소스 코드를 가져와서 가장 먼저 `파서(Parser)`에게 넘깁니다. 파서는 소스 코드를 분석한 후 `AST(Abstract Syntax Tree), 추상 구문 트리`로 변환합니다. 이 `AST`를`Ignition`에게 넘기는데 `Ignition`은   자바스크립트를 `바이트 코드(Bytecode)`로 변환하는 인터프리터입니다. 원본 소스 코드보다 컴퓨터가 해석하기 쉬운 바이트 코드로 변환함으로써 원본 코드를 다시 `파싱(Parsing)`해야하는 수고를 덜고 코드의 양도 줄이면서 코드 실행 때 차지하는 메모리 공간을 줄일 수 있습니다.

<br>

이후 이 바이트 코드를 실행함으로써  소스 코드가 실제로 작동하게 되고, 그 중 자주 사용되는 코드는 `TurboFan`으로 보내져서 `Optimized Machine Code`, 즉 최적화된 코드로 다시 컴파일됩니다. 그러다가 다시 사용이 덜 된다 싶으면 `Deoptimizing` 하기도 합니다.

<br>

### Node.js

이러한 V8엔진을 활용하여 빌드된 Javascript 런타임이 Node.js입니다. Javascript를 브라우저 외에 다른 환경에서도 사용할 수 있게 해주는 런타임입니다.