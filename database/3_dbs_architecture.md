# 데이터베이스 시스템 아키텍쳐

![스크린샷 2021-09-06 오후 8 42 26](https://user-images.githubusercontent.com/70752848/132212260-1865b0d7-f0f6-408d-99fd-e168327a194a.png)

- 데이터 정의어 컴파일러(DDL compiler) 모듈
  - 테이블 생성 요청시 테이블을 파일 형태로 DB에 만들고, 테이블에 대한 명세를 시스템 카탈로그에 저장
- 질의 처리기(query processor) 모듈
  - 데이터 조작어를 수행하는 최적의 방법을 찾는 모듈을 통해서 기계어 코드로 번역
- 런타임 DB 관리기 모듈
  - 디스크에 저장된 DB를 접근
- 트랜잭션 관리 모듈
  - 동시성 제어 모듈
  - 회복 모듈

## DB API(Application Program Interface)

- ODBC(Open Database Connectivity)
  - 거의 산업계의 표준, 윈도우 운영체제 에서 주로 사용

![스크린샷 2021-09-06 오후 8 51 38](https://user-images.githubusercontent.com/70752848/132213318-779d19b2-dd6d-4ab9-95f6-3e4962f697ac.png)

- JDBC(Java Database Connectivity)
  - 자바를 위한 드라이버, 자바가 운영되는 모든 플랫폼에 지원

## 중앙 집중식 DBS(centeralized database system)

- DBS 가 하나의 컴퓨터 시스템에서 운영

![스크린샷 2021-09-06 오후 8 53 13](https://user-images.githubusercontent.com/70752848/132213551-f2bcf436-4dc9-4d75-962b-71d1709122e1.png)

## 분산 DBS(distributed database system)

- 여러 사이트에 데이터 자체가 분산되어 있으며, 여러 컴퓨터 시스템에서 운영

![스크린샷 2021-09-06 오후 8 54 24](https://user-images.githubusercontent.com/70752848/132213682-60278f67-a6b6-481b-b364-e7d80b63fd4d.png)

## 클라이언트-서버 DBS

- 자체 컴퓨팅 능력을 가진 클라이언트를 통해 DB 서버를 접근
- 하나의 DB 서버에 저장
- 시스템 기능이 서버와 클라이언트에 분산
- 서버는 데이터를 저장하고 DBMS를 운영하면서 여러 클라이언트에서 온 질의를 최적화하고, 권한 감사를 수행하고, 동시성 제어와 회복 기능을 수행하고, 무결성을 유지하며, 접근을 관리함
- 클라이언트는 사용자 인터페이스를 관리하고 응용들을 수행

![스크린샷 2021-09-06 오후 8 58 00](https://user-images.githubusercontent.com/70752848/132214072-7bf95d2f-d7b8-4d34-84c5-a0c1fffaacf1.png)

- 2층 모델
  - 클라이언트와 DB
  - 서버가 직접 연결된
- 3층 모델
  - 클라이언트와 DB
  - 서버 사이에 응용 서버 추가
- 장점
  - DB를 보다 넓은 지역에서 접근 가능
  - 성능 향상, 하드웨어 비용 절감
  - 다양한 컴퓨터 시스템을 사용 가능
- 단점
  - 보안이 다소 취약할 수 있음

![스크린샷 2021-09-06 오후 9 02 25](https://user-images.githubusercontent.com/70752848/132214571-1de088c8-02fc-4323-bc63-43b0202e9958.png)
