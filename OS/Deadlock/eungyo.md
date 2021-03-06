# 교착 상태(Deadlock)의 4가지 조건에 대해 알고있나요?

교착 상태는 일련의 프로세스들이 CPU, memory space 등의 자원을 기다리며 block된 상태를 뜻합니다. 

이러한 교착 상태가 발생되는 네 가지 조건은 상호 배제, 비선점, 보유대기, 순환대기가 있습니다.

상호 배제는 매 순간 하나의 프로세스만이 자원을 사용할 수 있음을 뜻합니다. 만약 여러 프로세스가 자원을 동시에 사용할 수 있다면 자원을 기다리는 일이 없을 것입니다.

비선점이란 프로세스는 자원을 스스로 내어놓을 뿐, 강제로 빼앗기지 않음을 뜻합니다. 선점형 스케줄링처럼 우선순위에 따라 자원을 선점하게 된다면 교착상태가 생기지 않을 것입니다.

보유대기란 자원을 가진 프로세스가 다른 자원을 기다릴 때 보유 자원을 포기하지 않고 계속 가지고 있음을 뜻합니다. 만약 자원을 사용 시 전부 사용하는 것이 아니면 전부 포기하게 만든다면 교착상태가 생기지 않습니다.

순환대기란 자원을 기다리는 프로세스 간 싸이클이 형성되어야 합니다. 가령 프로세스1이 프로세스2의 자원을 기다리고, 프로세스2가 3의 자원을, 3이 1의 자원을 기다린다면 싸이클이 형성되고 교착상태가 일어날 것입니다.