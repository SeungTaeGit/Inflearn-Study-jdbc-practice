# 1. 스프링 JDBC 이해하기

이 리포지토리는 [강의 출처, 예: 김영한 님의 스프링 DB 1편] 강의를 수강하며 JDBC의 원리를 학습하고 실습한 내용을 기록한 공간입니다.

---

## 2. 학습 목표

* JDBC API의 사용법과 작동 원리 이해
* JDBC 드라이버 매니저와 커넥션 풀의 차이 학습
* 반복적인 JDBC 코드를 리팩토링하는 과정(템플릿 메소드 패턴) 경험

---

## 3. 핵심 학습 내용

* **JDBC 커넥션:** `DriverManager`를 통한 연결과 `DataSource`를 사용한 연결의 차이점을 배웠습니다.
* **트랜잭션:** 트랜잭션의 개념과 `setAutocommit(false)`를 통한 수동 관리 방법을 실습했습니다.
* **예외 처리:** JDBC 사용 시 발생하는 `SQLException`을 `try-catch-finally`로 처리하고, `close()`의 중요성을 확인했습니다.

---

## 4. 사용 기술

* **Language:** Java
* **Framework:** Spring (또는 Spring Boot)
* **Database:** H2 (또는 MySQL)
* **Build Tool:** Gradle

---

**예시:**
* **문제:** `JdbcSQLIntegrityConstraintViolationException: NULL not allowed for column "MEMBER_ID"` 에러 발생
* **원인:** `save()` 메소드 테스트 시, `Member` 객체에 `memberId`를 `null`로 전달함.
* **해결:** 테스트 코드에서 `member.setMemberId("testId")`와 같이 ID 값을 명시적으로 설정하여 해결.
