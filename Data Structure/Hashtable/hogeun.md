# Hashtable에 대해 간단히 설명해보세요

<br>

![img](hogeun.assets/315px-Hash_table_3_1_1_0_1_0_0_SP.svg.png)

> 해쉬 함수를 통해 Key 값이 배열의 인덱스에 매핑되는 모습 (출처 : https://en.wikipedia.org/wiki/Hash_table)

<br>

해시 테이블은 **Key-Value** 형태로 데이터를 저장하는 자료구조로서, 데이터의 검색이나 삽입, 삭제가 평균적으로 O(1)의 상수 시간 복잡도를 갖습니다.

<br>

작동원리를 간단히 설명하면, 먼저 해시 테이블은 Key 값을 데이터를 저장할 위치값으로 바꿔주는 **해시 함수(Hash Function)**와 Value 값을 저장하는 **배열 구조(bucket)**로 구성됩니다. Key 값과 해시 함수가 인덱스를 지정하면 배열의 해당 위치에 Value 값이 저장되고, 조회되는 방식도 동일합니다.

<br>

여기서 깊이 들어간다면, 어떠한 해시 함수를 사용하는가, 서로 다른 Key 값에 대해 해시 함수가 같은 위치를 지정해주는 상황, 즉 해시 충돌에 대해 어떻게 처리하는가에서 원리가 달라질 수 있습니다.

<br>

매우 유용한 자료구조이기 때문에 대부분의 언어에서 내장 데이터 타입으로 지원하고 있으며, Python의 Dictionary, JavaScript의 Object, JAVA의 Hashtable이 그 예시입니다.

<br>

![img](hogeun.assets/450px-Hash_table_5_0_1_1_1_1_1_LL.svg.png)

> 체이닝(Chaining)을 통해 해쉬 충돌에 대처하는 모습 (출처 : https://en.wikipedia.org/wiki/Hash_table)

<br><br>

> 출처 목록
>
> * https://en.wikipedia.org/wiki/Hash_table
> * [노마드 코더 - 개발자라면 꼭 알아야할 Hash Table 의 모든 것!](https://www.youtube.com/watch?v=HraOg7W3VAM)
> * [[DS] 해쉬 테이블(Hash Table)이란?](https://baeharam.netlify.app/posts/data%20structure/hash-table)

<br><br>

Fin.