# Python에서 is와 ==의 차이를 설명하시오

python에서 `is` 와 `==` 은 모두 두 데이터가 같은지 여부를 판단하는 **비교 연산자** 입니다.

<br>

다만 같다고 판단하는 수준에서 차이가 있는데, `==` 는 두 데이터의 **값이 같다면** 같다고 판단하는 반면, `is` 는 두 데이터의 **주소값이 같아야**, 즉 둘이 똑같은 데이터인지를 판단합니다.

<br>

만약 같은 값으로 선언된 두 변수가 있다면, `int` `bool` `string` 데이터에서는 `==` 나 `is` 의 결과가 `True` 일테지만, 그 외에 `list` `dict` `set` `tuple` `float` 데이터에서는 `==` 의 결과는 `True` 이지만, `is` 의 결과가 `False` 일 것입니다.

<br><br>

Fin.
