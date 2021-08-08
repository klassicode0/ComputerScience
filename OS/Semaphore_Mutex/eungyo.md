# 다수의 프로세스나 스레드가 공유 자원에 동시에 접근하는 것을 제어하는 방법을 설명해주세요.

세마포어와 뮤텍스가 있습니다.

먼저 세마포어는 세마포어 변수, semWait 연산, semSignal연산으로 이루어져 있습니다. 세마포어 변수는 정수로 해당 정수 값 만큼 사용자 동시 접근을 할 수 있습니다. semWait연산은 세마포어 값을 감소시킵니다. 값이 음수가 되면 semWait를 호출한 프로세스는 블록됩니다. semSignal 연산은 세마포어 값을 증가시킵니다. 만약 값이 0이하이면 semSignal 연산에 의해 블록된 프로세스들을 깨웁니다. 이러한 세마포어는 카운팅 세마포어 / 이진 세마포어로 나뉩니다. 카운팅 세마포어는 앞서 말씀드린 것처럼 세마포어 변수 값이 0이상의 수입니다. 그에 비해 이진 세마포어는 초기값이 0 또는 1만 가능합니다. 이는 뮤텍스와 유사합니다.

뮤텍스는 임계영역에 들어갈 때 lock을 걸어 다른 프로세스가 접근하지 못하도록 막고, 임계영역에서 나왔을 때 해당 lock을 해제하는 방식입니다. 카운팅 세마포어와 달리 오직 한개의 프로세스만 자원에 접근할 수 있습니다.