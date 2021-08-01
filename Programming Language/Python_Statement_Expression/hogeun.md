# Statement와 Expression의 차이를 설명해보아라

<br>

### Statement, 문장

statement는 모든 코드를 구성하는 가장 기본 단위로, ***무언가를 수행합니다.*** (Statements Do Something.) statement는 simple statement와 compound statement로 구분됩니다.

* ***simple statement는 세미콜론(;)으로*** 구분하면 나열 가능합니다.
* ***compound statement는 콜론(:)으로 header와 block을 구분하여*** 작성해야 하며, `if`, `for`, `while`, `def`, `class`, `try`, `with` 가 그 예시입니다.

<br><br>

### Expression, 표현식

expression은 statement의, 특히 simple statement의 한 종류로, ***항상 하나 이상의 값을 생성합니다.*** (Expressions produce at least one value.)

또한 ***괄호로 감싸면 object로 표현될 수 있습니다.*** 아래는 expression의 예시입니다.

* 데이터 : `23`  `'0b10011'`
* 이름 : `foo`  `bar`  `length`
* 호출식 : `foo(x)`  `bar(x)`
* lambda : `lambda a, b: (a ** 2 + b ** 2) ** 0.5`
* conditional expression : `'odd' if a % 2 else 'even'`
* comprehension : `n ** 2 for n in range(10)`
* 다양한 연산자를 포함하는 statement : `x < 10`  `x + 1`

<br>

반면 아래의 예시는 object로 표현될 수 없는 statement들로, expression이 아닙니다. (단, `yield`는 async 함수 내에서 사용될 경우 expression이 될 수 있으며, 이 때 가독성을 위해 괄호를 필수적으로 붙여야 합니)

* 대입연산자를 포함하는 statement : `x = 10`
* `break`  `continue`  `return`  `yield`  등

<br>

expression를 괄호로 감싸 object로 만들면 일반 object와 동일하게 다음의 위치에서 사용할 수 있습니다.

* 대입연산자 뒤에
* 함수의 인자로
* return 뒤에

<br><br>

> 출처 목록
>
> * **ssafy 수업 내용**
> * [**stackoverflow** - What is the difference between an expression and a statement in Python?](https://stackoverflow.com/questions/4728073/what-is-the-difference-between-an-expression-and-a-statement-in-python)
> * [**stackoverflow** - yield - statement or expression?](https://stackoverflow.com/questions/20142450/yield-statement-or-expression)
> * [**Python docs** - Yield expressions](https://docs.python.org/3/reference/expressions.html#yield-expressions)

<br><br>

Fin.