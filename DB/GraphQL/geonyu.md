# GraphQL이란?

> 페이스북에서 만든 쿼리 언어로 웹 클라이언트가 데이터를 서버로부터 효율적으로 가져오는 것이 목적입니다.

## SQL과의 비교

sql은 데이터베이스 스템에 저장된 데이터를 효율적으로 가져오는 것이 목적인 반면 gql은 웹 클라이언트가 데이터를 서버로부터 효율적으로 가져오는 것이 목적. 따라서 sql의 statement는 주로 백엔드 시스템에서 작성하고 호출하지만 gql은 클라이언트 시스템에서 작성하고 호출하게 된다.



## 특징

gql은 어떠한 특정 데이터베이스나 플랫폼에 종속적이지 않다. 따라서 일반적으로는 L7의 http post 메서드와 웹소켓 프로토콜을 활용하지만 필요에 따라서는 L4의 TCP/UDP를 이용하거나 L2의 이더넷 프레임을 활용할 수 있다.



https://tech.kakao.com/2019/08/01/graphql-basic/