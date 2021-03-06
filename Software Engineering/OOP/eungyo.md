# OOP의 특징과 5대 원칙에 대해 설명하시오.

OOP의 특징은 필요한 데이터를 추상화 시켜 상태와 행위를 가진 객체로 프로그램을 구성한다는 것입니다. 객체 간의 상호작용을 통해 로직을 구성하기 때문에 재사용이 용이하고 유지보수가 쉽습니다.

이러한 OOP의 5대 원칙에 대해 말씀드리겠습니다.

첫째, 단일 책임의 원칙(SRP)입니다. 클래스는 한 가지 기능만 가지며 한 가지 책임을 수행하는데 집중되어야 한다는 것입니다. 이러한 원칙을 따르면 클래스를 여러가지로 분할하여 유연하게 설계할 수 있습니다.

둘째, 개방 폐쇄의 원칙(OCP)입니다. 소프트웨어의 구성요소는 확장에는 열려있으나, 변경에는 닫혀있어야 한다는 것입니다. 추가 사항이 발생하더라도 기존 구성은 변경하지 않지만 확장에 대한 가능성은 열어두어야 한다는 것입니다.

셋째, 리스코브 치환의 원칙(LSP)입니다. 사용자의 관점에서 기능에 영향을 미치지 않고 자식 클래스를 부모 클래스로 대체할 수 있어야 한다는 것입니다. 이는 상속의 기본적인 원리입니다.

넷째, 인터페이스 분리의 원칙(ISP)입니다. 한 클래스는 자신이 사용하지 않는 인터페이스는 구현하지 말아야 한다는 것입니다. 인터페이스를 분리함으로써 의존성을 약화시켜 리팩토링이 용이해집니다.

다섯째, 의존성 역전의 원칙(DIP)입니다. 고 수준 모듈은 저 수준 모듈에 의존하면 안 된다, 즉 하위 레벨에서의 변경으로 인해 상위 레벨이 영향받으면 안 된다는 것입니다. 이 원칙을 준수하면 유지 관리가 편해지지만, 새로운 클래스 구현이 어려울 수 있습니다.