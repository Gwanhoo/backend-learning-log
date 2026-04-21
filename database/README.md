# MongoDB (Database Design)

유연한 데이터 구조가 필요한 협업 시스템에서
MongoDB를 사용하여 데이터 모델을 설계하고 구현했습니다.

---

## 1. 왜 사용했는가

프로젝트와 태스크 구조가 고정되지 않고 유동적으로 변화하기 때문에
스키마 변경이 자유로운 NoSQL 데이터베이스가 필요했습니다.

또한 JSON 기반 데이터 구조를 그대로 저장하고 활용할 수 있어
개발 속도와 유연성을 확보할 수 있었습니다.

---

## 2. 개념 정리

### Collection

* 관계형 데이터베이스의 테이블과 유사한 개념

### Document

* JSON 형태로 저장되는 데이터 단위

### Schema-less

* 고정된 스키마 없이 유연하게 구조 변경 가능

---

## 3. 적용 과정

* User / Project / Task 단위로 컬렉션 설계
* ObjectId를 활용하여 데이터 간 관계 구성
* REST API와 연결하여 CRUD 기능 구현

예시:

* users
* projects
* tasks

---

## 4. 문제점

* 관계형 DB처럼 JOIN이 없어 데이터 조회 시 불편함 발생
* 참조 관계가 많아질수록 구조가 복잡해짐

---

## 5. 해결

* 필요한 데이터는 일부 중복 저장 (denormalization)
* 조회 성능을 고려하여 데이터 구조 재설계
* 자주 조회되는 데이터는 문서 내부에 포함하도록 설계

---

## 데이터 구조 예시

게시글(Post) 기준 데이터 구조

```json
{
  "_id": "postId",
  "title": "10-29 태그 기능",
  "content": "태그 기능",
  "tags": ["Node.js", "Python", "AI", "소프트웨어공학과", "소공과"],
  "tags_lc": ["node.js", "python", "ai", "소프트웨어공학과", "소공과"],
  "authorId": "userId",
  "authorName": "qwer",
  "createdAt": "2025-10-29T00:36:31.073Z"
}

---

