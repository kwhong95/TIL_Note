# 1. 데이터베이스

> 조직체의 응용 시스템들이 **공유**해서 사용하는 운영 데이터(operational data)등이 **구조적**으로 **통합**된 모임이다. 데이터베이스의 구조는 사용되는 데이터 모델에 의해 결정된다.

## 특징

- 데이터의 **대규모 저장소**로서, 여러 사용자에 의해 동시 사용됨
- 모든 데이터가 **중복**을 **최소화**하면서 통합됨
- 운영 데이터뿐만 아니라 데이터에 관한 설명(스카마 또는 메타데이터)을 포함함
- 프로그램과 데이터 간의 **독립성**이 제공됨
- 효율적으로 접근이 가능하고 질의 할 수 있음

## 데이터베이스 관리 시스템(DBMS: Database Management System)

> 데이터베이스를 정의, 질의어 지원, 리포트 생성 등의 작업을 수행하는 소프트웨어

# 2. 데이터베이스 시스템(DBS)

## 데이터베이스 시스템의 구성

> 데이터베이스, 사용자, 응용프로그램, DBMS, 하드웨어로 구성

<img width="574" alt="스크린샷 2021-09-06 오후 3 10 02" src="https://user-images.githubusercontent.com/70752848/132168702-a84b526d-f1e9-44f7-992f-d12afb45de56.png">

> 데이터베이스 시스템의 구성요소

![스크린샷 2021-09-06 오후 3 11 42](https://user-images.githubusercontent.com/70752848/132168806-26d8e678-bdfa-4dff-bece-ecf550beca8a.png)

## 데이터베이스 스키마

### 스키마(Schema)

![스크린샷 2021-09-06 오후 3 12 41](https://user-images.githubusercontent.com/70752848/132168883-e04c6e65-5e73-4f62-a15b-26f2a4bcf488.png)

- 전체적인 데이터베이스의 구조
- 자주 변경되지 않음
- 내포(instension) 라고 부름

### 데이터 베이스 상태 (인스턴스)

![스크린샷 2021-09-06 오후 3 13 48](https://user-images.githubusercontent.com/70752848/132168983-f00a0cac-6988-4e46-a0f7-c0737dbd576c.png)

- 특정 시점의 데이터베이스의 내용
- 계속 변하는 특성
- 외연 (extension) 라고 부름

## DBS의 구성 - 데이터베이스

### 데이터베이스

- 조직체의 응용 시스템들이 공유해서 사용하는 운영 데이터들이 구조적으로 통합된 모임
- 시스템 카탈로그(또는 데이터 사전)와 저장된 데이터 베이스로 구분 가능
- **시스템 카탈로그(system catalog)**
  - 시스템 그 자체에 관련이 있는 다양한 객체에 관한 정보를 포함하는 시스템 데이터베이스
  - 저장된 데이터베이스의 스키마 정보를 유지

![스크린샷 2021-09-06 오후 3 18 26](https://user-images.githubusercontent.com/70752848/132169426-694d5ad3-e872-423b-a168-de1abe909250.png)

## DBS의 구성 - 사용자

### 사용자

- 여러 부류로 분류 가능
- 갖추어야할 지식 수준

| 구분            | SQL언어 | 프로그래밍 능력 | DBMS 지식 | 데이터 구성 |
| --------------- | ------- | --------------- | --------- | ----------- |
| 일반 사용자     | 없음    | 없음            | 없음      | 없음        |
| SQL 사용자      | 높음    | 없음            | 보통      | 보통        |
| 응용 프로그래머 | 높음    | 높음            | 보통      | 보통        |
| DB 관리자       | 높음    | 보통            | 높음      | 높음        |

## DBS의 구성 - 하드웨어

### 하드웨어

- 데이터베이스는 디스크와 보조 기억 장치에 저장되며, DBMS에서 원하는 정보를 찾기 위해서는 디스크의 블록들을 주기억장치로 읽어 들여야 하며, 계산이나 비교 연산들을 수행하기 위해 중앙 처리 장치가 사용됨
- DBMS 자체도 주기억 장치에 적재되어 실행되어야 함

## 데이터베이스 시스템의 요구사항

### 요구사항

- 데이터 독립성
- 효율적인 데이터 접근
- 데이터에 대한 동시 접근
- 백업과 회복
- 종복을 줄이거나 제어하며 일관성 유지
- 데이터 무결성
- 데이터 보안
- 쉬운 질의어
- 다양한 사용자 인터페이스

# 3. 파일 시스템 VS DBMS

## 파일 시스템

### 파일 시스템을 사용한 기존의 데이터 관리

- 과거의 데이터를 관리하기 위해 파일 시스템 사용
- 데이터 파일로 관리 가능하도록 파일을 생성, 삭제, 수정, 검색 기능 제공
- 퍼일 접근 방식이 응용 프로그램 내에 상세히 표현되므로 데이터에 대한 응용 프로그램의 의존도가 높음

![스크린샷 2021-09-06 오후 3 29 03](https://user-images.githubusercontent.com/70752848/132170547-7bae2f4c-e89f-4aa8-b7f8-2e8158daeea4.png)

> 파일 시스템은 각 응용프로그램이 독립적으로 다루기 때문에 데이터들이 중복으로 저장될 수 있고 동시에 파일을 다루기 때문에 데이터의 일관성 훼손될 수 있음

## EXAMPLE 1

### [Program 1]

- 데이터를 프로그램 내부에 저장
  - C 언어의 구조체 `BOOK`을 먼저 선언하고 `main()`프로그램에서 구조체 배열 변수 `BOOK[]`에 데이터를 저장
  - 도서 데이터는 프로그램 내 구조체 변수에 저장됨
  - _문제점_ : 새로운 데이터가 생길 시 프로그램을 수정한 후 다시 컴파일해야 함

![스크린샷 2021-09-06 오후 3 34 12](https://user-images.githubusercontent.com/70752848/132171069-934ea44e-29ad-4ea0-bdac-1f3a27de9416.png)

## EXAMPLE 2

### [Program 2]

- 데이터를 프로그램 내부에 저장

  - `BOOK` 데이터 구조를 먼저 선언하고 `main()` 프로그램에서 파일로부터 데이터를 불러와 구조체 배열 변수 `BOOK[]`에 저장
  - 새로운 데이터가 추가되어도 프로그램을 수정할 필요 없음
  - _문제점_ : 같은 파일을 두 개의 프로그램이 공유하는 것이 운영체제의 도움 없이 불가능

  ![스크린샷 2021-09-06 오후 3 38 30](https://user-images.githubusercontent.com/70752848/132171547-8fb88ce4-0192-4ada-b017-cb9072c264eb.png)

  ## 파일 시스템의 단점

  ### 단점

  - 데이터가 많은 파일에 중복되어 저장 됨
  - 다수 사용자들을 위한 동시성 제어가 제공되지 않음
  - 검색하려는 데이터를 쉽게 명시하는 질의어가 제공되지 않음
  - (사용자별로) 보안 조치가 미흡
  - 회복 기능이 없음
  - 프로그램-데이터 독립성이 없으므로 유지보수 비용이 많이 소요됨
  - 파일을 검색하거나 갱신하는 절차가 상대적으로 복잡하기 때문에 프로그래머의 생산성이 낮음
  - 데이터의 공유와 융통성 부족

#### 간단한 MOCK 데이터, 수정이 필요없는 데이터는 CSV, JSON과 같은 파일 시스템으로 사용함

> 파일 시스템의 데이터 중복성, 데이터의 중속성의 문제로 <span style="color:red">**데이터베이스 관리 시스템**</span>이 등장하게 됨

## DBMS를 사용한 데이터베이스 관리

- 여러 사용자와 응용 프로그램들이 데이터베이스를 공유 - **동시성** 보장
- 사용자의 질의를 빠르게 수행할 수 있는 인덱스 등의 접근 경로를 DBMS가 자동적으로 선택하여 수행 - **질의어** 제공
- 권한이 없는 사용자로부터 데이터베이스를 보호
- 여러 사용자에 적합한 다양한 인터페이스를 제공
- 무결성 제약조건을 자동적으로 유지
- 시스템 고장 시 데이터베이스를 고장 전 상태로 회복
- 프로그램 영향 없이 구조 변경 가능 - **프로그램-데이터 독립성**

## DBMS의 장점

- 중복성 및 불일치 감소
- 시스템 개발 유지 비용 감소
- 표준화 용이
- 보안 향상
- 무결성 향상
- 조직체 요구사항 식별 가능
- 다양한 유형 고장으로부터 데이터베이스 회복 가능
- 공유 및 동시접근 가능

## DBMS의 단점

- 추가 하드웨어 구입 비용이 들고, 자체 구입 비용이 상당히 비쌈
- 직원 교육 비용도 많이 소요
- 비밀과 프라이버시 노출등의 단점 존재 가능
- 초기 투자 비용이 크거나, 오버헤드가 너무 크거나, 응용이 단순하고 잘 정의되었으며 변경되지 않을 것으로 예상되거나, 엄격한 실시간 처리 요구사항이 있거나, 데이터에 대한 다수 사용자의 접근이 필요하지 않을 때는 DBMS를 사용하지 않는 것이 바람직할 수 있음

## EXAMPLE

### [Program 3]

- 데이터를 DBMS 내부에 저장

  - 데이터의 정의와 데이ㅓ 값을 DBMS가 관리
  - DBMS는 데이터 정의, 데이터 변경 드으이 작업을 할 수 있는 별도의 프로그램 존재
  - 프로그램에 데이터 정의나 데이터 값을 포함하지 않기 때문에 데이터 구조가 바뀌어도 다시 컴파일할 필요 업음

  ![스크린샷 2021-09-06 오후 3 58 32](https://user-images.githubusercontent.com/70752848/132173830-b57bef5c-f4f8-4c47-bbb7-f32b8cfd5eaf.png)

## 파일 시스템과 DBMS의 비교

| 구분                | 파일 시스템                     | DBMS                                   |
| ------------------- | ------------------------------- | -------------------------------------- |
| 데이터 정의         | 응용 프로그램                   | DBMS                                   |
| 데이터 저장         | 파일 시스템                     | 데이터베이스                           |
| 데이터 접근 방법    | 응용프로그램이 파일에 직접 접근 | 응용프로그램이 DBMS에 파일 접근을 요청 |
| 사용 언어           | 자바, C++, C 등                 | 자바, C++, C등과 SQL                   |
| CPU/주기억장치 사용 | 적음                            | 많음                                   |

![스크린샷 2021-09-06 오후 4 01 39](https://user-images.githubusercontent.com/70752848/132174224-ff71be53-ba2c-47bd-9142-18e67e2da454.png)