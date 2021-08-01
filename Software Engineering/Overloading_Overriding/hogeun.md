# Overloading & Overriding

<br>

오버로딩과 오버라이딩은 **모두 객체 지향 프로그래밍에서 다형성에** 대한 기능입니다.

<br>

먼저 오버로딩은 하나의 메소드에서 인자를 다르게 대입했을 때 서로 다른 기능을 수행하도록 하는 방법입니다. 의사코드로 표현하면 다음과 같습니다.

```
class ABC:
	def funcA():
		print('인자로 주어진 데이터가 없습니다.')
	def funcA(int a):
		print('인자로 숫자 {a}가 주어졌습니다.')
	def funcA(array li[]):
		print('인자로 배열 {li}가 주어졌습니다.')
```

<br>

오버라이딩은 상위 클래스를 상속받는 하위 클래스에서 상위 클래스의 메소드를 수정하여 사용하는 것입니다. 의사코드로 표현하면 다음과 같습니다.

```
class Parent:
	def funcA():
		print('나는 청주 곽씨 10대손입니다.')

class Child(Parent):
	def funcA():
		print('나는 청주 곽씨 11대손입니다.')

class NaughtyChild(Parent):
	def funcA(num):
		print('난 내놓은 자식이라 내 마음대로 할거지롱.')
		return(num)
```

<br>

아래 NaughtyChild와 같이 Parent 클래스의 메소드와 전혀 다르게 동작하는 메소드로 오버라이딩하는 것도 가능합니다.

<br><br>

Fin.