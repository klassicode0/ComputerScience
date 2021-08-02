# 프로세스와 스레드의 차이를 설명해보아라.

<br>

먼저 프로그램부터 설명하겠습니다. **프로그램은 컴퓨터의 저장장치에 보관되어 있는 정적인 상태**의 '작업 절차서'입니다. 이 절차서에는 어떤 데이터를 이용해 어떤 작업을 해야하는지 등이 적혀 있습니다. 예를 들자면 스파게티의 레시피가 프로그램이라고 할 수 있습니다.

<br>

사용자나 운영체제에 의해 이 프로그램이 실행되면 **메모리에 올라와 동적인 상태가 되는데, 이 동적인 상태의 프로그램을 프로세스**라고 합니다. 앞서 설명한 대로 프로그램이 레시피라면 프로세스는 레시피 대로 직접 스파게티를 조리하는 것입니다.

<br>

이렇게 프로그램이 실행되어 프로세스가 생성되면, 운영체제는 이 **프로세스를 컴퓨터의 작업소인 CPU가 수행할 수 있는 실행 단위로 만들어 CPU에 전달합니다. 이 전달 단위 하나하나가 스레드**입니다. 채소를 다듬고, 스파게티 면을 삶거나 하는 각각의 조리 행위가 스레드에 해당됩니다.

<br><br>

> 출처 목록
>
> * **쉽게 배우는 운영체제** / 한빛아카데미

<br><br>

Fin.