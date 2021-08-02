# Intro

>운영체제의 핵심!
>
>컴퓨터 내의 자원을 유저 application이 사용할 수 있도록 만들어주는 프로그램



# Kernal

운영체제에서 프로세스, 메모리, 저장장치 관리를 한다. 무척 핵심적인 기능이다. 유저의 프로그램이 커널에 접근하게 될때 System call interface를 통하여 이루어진다.

어렵죠...

## 복습을 해보겠습니다. 

* 컴퓨터는 HW와 SW로 구분됩니다.

* SW는 운영체제(OS)와 응용프로그램(Application program)으로 구분됩니다.
  - 운영체제는 윈도우, mac 이러한 것들 
  - 응용프로그램은 워드, 카트라이더, 크롬 등... 셀 수 없이 많습니다.
* 그 중 운영체제는 커널과 스스템 프로그램으로 구분됩니다.

이제 커널의 가계도를 파악했습니다.

커널은 운영체제에서 핵심 기능입니다. 컴퓨터의 자원들을 관리합니다. 컴퓨터의 자원이란 메인 메모리, 저장장치 등이 있습니다. 

컴퓨터의 자원은 제한적입니다. 반면 프로그램은 많죠 그러기에 커널이 각 프로그램의 프로세스마다 얼마만큼 자원을 사용해야 하는지 결정해줍니다. <- 이를 **스케쥴링**이라고 합니다!

 커널은 대부분 C코드로 작성되어 있으며 일부 어셈블리어로 작성되어있습니다. 이 녀석들은 사용자에게 친화적이지 않습니다. (중요한 컴퓨터의 자원을 관리하니 사용자와 친해도 문제죠!) 



## 그럼 우리는 커널을 느낄 수 없는 것일까요?

아닙니다.

우리가 일반적으로 사용하는 응용프로그램으로는 많은 기능을 구현하기 힘들기 때문에 커널의 도움을 받아 더 깊은 작업을 수행하게 됩니다. 보통 유저모드에서 수행할 수 없는 작업을 커널모드로 전환한 후 깊은 작업을 수행할 권한을 부여 받습니다. 이 때 응용프로그램이 커널의 기능을 사용하게 하는 인터페이스를 system call이라 합니다.

mkdir도 system call입니다.



## 왜 이렇게 번거롭게...

보통 유저가 쉽게 운영체제의 치명적인 데이터를 수정/삭제하는 것을 막기 위해서 입니다.



## system call의 유형

1. 프로세서 제어(process Control)

2. 파일 조작(file manipulation)

3. 장치 관리(Device Management)

4. 정보 유지(Information maintenance)

5. 통신 (Communication)
