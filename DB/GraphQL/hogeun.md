# GraphQL에 대해 들어본 적 있나요? 설명해보세요

<br>

![image-20210708230132189](/Users/yeonglong/Library/Application Support/typora-user-images/image-20210708230132189.png)

> stateofjs 에서 실시한 설문조사의 결과, 가운데 GraphQL의 그래프를 보면 2016년부터 현재까지 긍정적으로 생각하거나 한번이라도 사용해본 개발자의 수가 급격하게 증가함을 볼 수 있다.

<br>

GraphQL은 페이스북에서 개발한 SQL과 같은 쿼리 언어입니다. 다만, 그 형태는 아래의 예시처럼 아주 다르게 생겼습니다. SQL문은 규칙적인 문자열의 형태라면, **GQL문은 계층화된 객체의 형태입니다.** 게다가 **응답문의 구조 또한 요청 쿼리의 구조와 동일합니다.**

<br>

먼저 형태적인 차이에 대해 설명하자면, 이렇게 다르게 생길 수 있는 까닭은 GQL 쿼리문을 해석하는 방식 덕분입니다. GQL에는 각각의 필드마다 **리졸버라는 쿼리문을 해석하는 함수가 있는데,** 위에서부터 쿼리문을 훑으며 새로운 필드가 나올 때마다 관련된 리졸버가 해당 데이터를 가져옵니다.

<br>

```
SELECT plot_id, species_id, sex, weight, ROUND(weight / 1000.0, 2) FROM surveys;
```

*sql 쿼리 예시*

```
{
  hero {
    name
    height
  }
}
```

```
{
  "hero": {
      "name": "Luke Skywalker",
      "height": 1.72
  }
}
```

*gql 쿼리와 응답 예시*

<br>

또다른 차이는 SQL을 위한 HTTP 엔드포인트는 여러개로 구분되지만, GQL은 쿼리문에 CRUD 정보가 포함되기 때문에 **엔드포인트가 단일합니다.** 또한, 여러 테이블에 분산된 데이터를 가져올 때도 SQL과 달리 GQL은 한번의 요청으로 완료될 수 있습니다.

<br>

제가 아는 마지막 차이는 SQL은 서버에서 DB로 날리는 쿼리문이라면, **GQL은 클라이언트에서 서버로 직접 날리는 쿼리문입니다.** 이러한 점 때문에 카카오 기술 블로그에서는 GQL은 퍼포먼스적인 측면보다 프론트엔드-백엔드 개발 협업문화의 변화를 불러올 수 있다는 점에서 기대된다고 평했습니다.

<br>

다만, 아직은 GraphQL에 대한 API를 제공하는 서비스가 많지 않습니다.

<br><br>

- https://tech.kakao.com/2019/08/01/graphql-basic/
- https://graphql.org/
- https://2020.stateofjs.com/en-US/technologies/datalayer/