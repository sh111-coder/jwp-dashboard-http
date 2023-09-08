# 톰캣 구현하기

## 🎯 1단계 - HTTP 서버 구현하기 & 2단계 - 로그인 구현하기

- [x] GET /index.html 요청이 들어오면 index.html 파일을 응답한다.

- [x] CSS, JS를 지원한다.
  - [x] Response Content-Type : text/css로 응답
  - [x] Response Content-Type : text/javascript로 응답

- [x] Query String을 파싱한다.

- [x] 로그인 여부에 따라 다른 페이지로 리다이렉트한다.
  - [x] 로그인에 성공하면 `index.html`로 리다이렉트한다.
  - [x] 로그인에 실패하면 `401.html`로 리다이렉트한다.

- [x] POST 방식으로 회원가입을 할 수 있다.
  - [x] `/register` 경로로 접근하면 `register.html`을 보여준다.
  - [x] 회원가입 버튼을 누르면 POST로 회원 가입 성공 후, `index.html`로 리다이렉트 한다.

- [x] 로그인 페이지에서도 로그인 버튼을 누르면 POST로 전송하도록 변경한다.

- [x] 쿠키와 세션을 활용해서 로그인을 유지한다.
 - [x] 요청 헤더, 응답 헤더에 쿠키 설정을 추가한다.
 - [x] 쿠키의 세션 값으로 로그인 여부를 체크한다.
   - [x] 로그인에 성공하면 세션 객체의 값으로 User를 저장한다.
   - [x] 로그인된 상태로 로그인 페이지에 접근하면 index.html 페이지로 리다이렉트한다.

---

## 🎯 3단계 - 리팩토링 & 4단계 - 동시성 확장하기

- [x] 분기별 처리 - Controller 구현하기
  - [x] HTTP Method에 따라 Controller 분리
  - [x] 허용하지 않는 HTTP Method 시 405 Status Code 응답

- [x] 동시성 확장하기
  - [x] Executors로 Thread Pool 적용
    - 기본 Max Thread 수 250으로 설정
  - [x] SessionManager 동시성 컬렉션 사용
