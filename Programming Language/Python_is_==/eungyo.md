# Python에서 is와 ==의 차이를 설명하시오.

`is`는 변수가 같은 객체를 가리키면 `True`이며, `==`는 변수가 같은 값을 가지면 `True`입니다.

```python
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(a is b) # True
print(a is c) # False
print(a == b) # True
print(a == c) # True
```

이러한 예제에서 `a is c`가 `False`인 이유는 `a`, `c`가 값은 `[1, 2, 3]`으로 같지만 서로 다른 객체를 가리키기 때문입니다. 반면 `a is b`가 `True`인 이유는 리스트인 `a`가 `b`에 할당되었을 때 `b`는 `a`와 같은 리스트를 가리키게 되기 때문입니다.

`a == b`와 `a == c`가 모두 `True`인 이유는 `a`, `b`, `c` 모두 `[1, 2, 3]` 이라는 같은 값을 가지기 때문입니다.