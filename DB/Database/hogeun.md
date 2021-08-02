# [DB] 데이터베이스를 한 문장으로 정의해보아라

<br>

데이터베이스는 특정 조직의 여러 사용자가 **'공유'**하여 사용할 수 있도록 **'통합**'해서 **'저장'**한 **'운영 데이터의 집합'**입니다.

* 공유 데이터 : 일반적으로 데이터베이스는 여러 사용자가 함께 사용합니다. 따라서 목적이 다른 여러 사용자를 두루 고려해야 합니다.
* 통합 데이터 : 데이터의 중복을 최소화하고, 통제 가능한 중복만을 허용해야 합니다. (효율성을 위해 중복을 의도적으로 허용하기도 합니다. 정규화와 비정규화.)
* 저장 데이터 : 컴퓨터가 접근 가능한 매체에 데이터를 저장해야 합니다.
* 운영 데이터 : 언제든 운영 가능하도록 지속적으로 유지되어야 합니다.



데이터베이스의 특징 4가지

* 실시간 접근성 real-time accessability : 사용자의 데이터 요구에 실시간으로 응답합니다
* 지속적 변화 continuous evolution : 데이터 CRUD를 통해 끊임없이 변화합니다.
* 동시 공유 concurrent sharing : 여러 사용자가 동시에 사용합니다.
* 내용 참조 content reference : 데이터의 index 값 뿐 아니라 데이터의 내용으로도 참조 가능합니다.

<br><br>

Fin.