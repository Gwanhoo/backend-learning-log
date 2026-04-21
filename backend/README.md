
# Backend (Node.js / Express)

클라이언트 요청을 처리하고 데이터 흐름을 관리하기 위해
Node.js와 Express 기반 서버 구조를 설계하고 구현했습니다.

---

## 1. 왜 사용했는가

프론트엔드에서 발생하는 요청을 처리하고
데이터를 저장 및 관리하기 위한 서버가 필요했습니다.

기능 단위로 API를 분리하고 유지보수성을 확보하기 위해 Express를 사용했습니다.

---

## 2. 개념 정리

### Node.js

* 이벤트 기반 비동기 처리 서버 환경
* 단일 스레드 기반으로 동작하지만, 비동기 처리를 통해 높은 처리 효율 제공

### Express

* 라우팅 및 미들웨어 기반 서버 프레임워크
* 요청 처리 흐름을 구조적으로 구성 가능

### REST API

* 자원을 URI로 표현
* HTTP 메서드(GET, POST, PUT, DELETE)를 통해 동작 정의

---

## 3. 적용 과정

* `/api` 기준으로 라우터를 분리하여 구조 설계
* 기능 단위로 컨트롤러 구성
* JSON 기반 요청/응답 구조 통일

예시:

* `/api/users`
* `/api/projects`
* `/api/tasks`

---

## 4. 문제점

* 초기에는 API 구조가 명확하지 않아 코드 관리가 어려웠음
* 비즈니스 로직이 한 파일에 몰려 가독성과 유지보수성이 떨어짐

---

## 5. 해결

* 라우터 / 컨트롤러 단위로 역할 분리
* 기능 단위로 파일 구조 재정리

예시 구조:

```
src/
├── routes/
├── controllers/
├── services/
```

---

## 💻 코드 예시

```js
app.use('/api/users', userRouter);
app.use('/api/projects', projectRouter);
app.use('/api/tasks', taskRouter);
```

---

## 📊 아키텍처 (추가 예정)

* Client → Router → Controller → Database 흐름 구조
* API 요청 처리 및 응답 반환 과정
