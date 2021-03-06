# 트랜잭션이란?

> 데이터베이스의 상태를 변환시키는 하나의 논리적 기능을 수행하기 위한 작업의 단위, 혹은 연산입니다.

## 특징

1. 데이터베이스 시스템에서 병행 제어 및 회복 작업시 처리 되는 작업의 단위
2. 하나의 트랜잭션은 commit 되거나 rollback 된다.

## 성질

### 1. 원자성

트랜잭션의 연산은 데이터베이스에 모두 반영되든지 아니면 전혀 반영되지 않아야 한다. 

트랜잭션 내의 모든 명령은 반드시 완벽히 수행되어야 하며, 모두 완벽히 수행되지 않고 어느 하나라도 오류가 발생하면 트랜잭션 전부가 취소되어야 한다.

### 2. 일관성

트랜잭션이 실행을 성공적으로 완료하면 항상 일관성 있는 데이터베이스 상태로 변환한다. 시스템이 가지고 있는 고정요소는 트랜잭션 수행 전과 트랜잭션 수행 완료 후의 상태가 같아야 한다.

### 3. 독립성(격리성)

둘 이상의 트랜잭션이 동시에 실행되는 경우 어느 하나의 트랜잭션 실행중에 다른 트랜잭션의 연산이 끼어들 수 없으며 수행중인 트랜잭션은 완전히 완료될 때까지 다른 트랜잭션에서 수행 결과를 참조할 수 없다.

### 4. 지속성

성공적으로 완료된 트랜잭션의 결과는 시스템이 고장나더라도 영구적으로 반영되어야 한다. 

https://coding-factory.tistory.com/226