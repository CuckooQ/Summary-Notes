# API

<br>

## 목차

#### [1. 정의](#정의)

#### [2. REST API](#REST-API)

- 정의
- 규칙
- HTTP Method
- Status Code
- General Header
- Request Header
- Response Header
- X Header
- Authorization Token
- Library

<br>

---

<br>

## 정의

- 데이터 교환 목적의 인터페이스

<br>

## REST API

### 정의

- 자원의 이름으로 구분해서 자원의 상태를 주고 받는 API

### 규칙

- '/'로 계층 관계 표현
- 긴 URL을 사용할 경우 '-' 사용
- URL 마지막에 '/' 사용 금지
- '\_' 사용 금지
- 파일 확장자 사용 금지
- 대문자 사용 지양

### HTTP Method

- GET
- HEAD
  - 콘텐츠가 없는 헤더 내용 요청
  - 헬스체크
  - 웹 서버 정보 확인
  - 버전 확인
  - 최종 수정일 확인
- POST
- PUT
- PATCH
- DELETE
- OPTIONS
  - 서버가 제공하는 메소드 요청
  - 응답 헤더 Allow에서 사용 가능한 메소드 확인 가능
- CONNECT
  - 양방향 연결 요청
- TRACE
  - 요청 내용이 서버에 도달했을 때의 내용 요청
  - 디버그용

### Status Code

#### 1XX

- 100
  - CONTINUE
  - 클라이언트로부터 일부 요청을 받은 상태이고, 나머지 요청을 기다리는 중
- 101
  - SWITCHING PROTOCOL
  - 클라이언트로부터 프로토콜 전환 요청을 받은 상태이고, 서버에서 승인중

#### 2XX

- 200
  - SUCCESS
- 201
  - CREATED
  - POST, PUT 요청의 응답
  - Content-Disposition 헤더를 통해 생성된 자원의 위치 전달 가능
- 202
  - ACCEPTED
  - 비동기 요청의 응답
  - 요청이 성공했으나 아직 동작을 수행하지 않은 상태
  - 콜백이나 폴링을 통해서 요청의 동작 완료 확인 가능
- 204
  - NO CONTENT
  - PUT, DELETE 요청의 응답

#### 3XX

- 301
  - MOVED PERMANENTLY
  - 요청한 리소스의 URL이 변경되었음을 의미하는 응답
  - 응답에 변경된 URL 정보가 포함
- 302
  - FOUND
  - 오청한 리소스의 URL이 일시적으로 변경되었음을 의미하는 응답
  - 응답에 변경된 URL 정보가 포함
- 304
  - NOT MODIFIED
  - 이전 요청 내용과 변화가 없음을 의미하는 응답
  - 캐싱 목적

#### 4XX

- 400
  - BAD REQUEST
  - 잘못된 요청
  - 응답에 에러 이유 정보가 포함
- 401
  - UNAUTHENTICATED
  - 비인증 상태
- 403
  - FORBIDDEN (UNAUTHORIZED)
  - 접근 권한이 없는 상태
- 404
  - NOT FOUND
- 405
  - METHOD NOT ALLOWED
  - 의도적으로 지원하지 않는 요청을 받은 상태
- 407
  - PROXY AUTHENTICATION REQUIRED
  - 비인증 상태이지만, 프록시를 통해서 인증할 것을 요구하는 상태
- 408
  - REQUEST TIMEOUT
- 409
  - CONFLICT
  - 클라이언트 요청들이 서버에서 충돌이 발생한 상태
- 410
  - GONE
  - 요청한 URL이 더이상 사용되지 않는 상태
- 411
  - LENGTH REQUIRED
  - 요청에 Content-Length 헤더가 필요
- 412
  - PRECONDITION FAILED
  - 요청의 헤더에 있는 전제 조건이 서버의 전제 조건과 일치하지 않는 상태
- 414
  - URL TOO LONG
- 429
  - TOO MANY REQUEST

#### 5XX

- 500
  - INTERNAL SERVER ERROR
- 501
  - NOT IMPLEMENTED
  - 의도하지 않게 지원하지 않는 요청을 받은 상태
- 502
  - BAD GATEWAY
  - 게이트웨이에서 작업한는 동안 문제가 발생
  - 서버 과부하
  - 클라이언트 네트워크 문제
- 503
  - SERVICE UNAVAILABLE
  - 서버가 요청을 처리할 준비가 되어 있지 않은 상태
  - 서버 중단
  - 서버 과부하
  - 사용 불가 페이지 표시 필요
  - Retry-After 헤더에 서버 복구 예상 시간을 포함
- 504
  - GATEWAY TIMEOUT
- 505
  - HTTP VERSION NOT SUPPORTED
  - 서버가 지원하지 않는 프로토콜 요청
  - 올바르지 못한 프로토콜 요청

### General Header

- Allow
  - 제공하는 메소드
- Cache-Control
- Content-Encoding
  - 큰텐츠 압축 방식
- Content-Length
  - 바이트 단위
- Content-Type
  - 콘텐츠의 MIME타입과 문자열 인코딩 방식
- Content-Language
- Date
- Etag
- Transfer-Encoding
  - Chunked방식에서의 콘텐츠 압축 방식
- Via
  - 중계 서버 이름, 버전, 호스트명

### Request Header

- Accept
  - 서버로부터 받을 콘텐츠 형식
- Accept-Charset
- Accept-Encoding
  - 서버로부터 받을 콘텐츠의 압축 방식
- Accapt-Language
- Authorization
  - 인증 토큰
- Cookie
  - 서버에 전송하는 쿠키
- Host
  - 서버의 포트 포함 도메인 네임
- Origin
  - 조작이 불가능한 요청 주소
- Referer
  - 조작이 가능한 요청 주소
- User-Agent
  - 클라이언트 정보

### Response Header

- Access-Control-Allow-Origin
  - 데이터 공유를 허용하는 도메인 주소
- Content-Disposition
  - 브라우저에서의 본문 표시 방법
  - inline
    - 화면 표시
  - attachment
    - 다운로드
- Content-Security-Policy
  - XSS 방지 헤더
- Location
  - 상태 코드 3XX나 201일 경우에 이동할 페이지를 알려주는 헤더
- Set-Cookie
  - 클라이언트에 저장할 쿠키

### X Header

- X-Forwarded
  - 요청이 거쳐온 서버
- X-Forwarded-For
  - 요청이 거쳐온 IP
- X-Forwarded-Host
  - 요청의 원래 서버 도메인
- X-Forwarded-Proto
  - 요청의 원래 서버 프로토콜
- X-Frame-Options
  - iframe태그 안에서의 페이지 렌더링 제어
- X-Content-Type-Options: nosniff
  - Content-Type 헤더 지정 형식과 일치하는 데이터만 로드

### Authorization Token

- Basic
  - Base64로 인코딩한 토큰
- Bearer
  - JWT 토큰
  - OAuth 토큰
- Digest
- HOBA
- Mutual

### Library

- XMR
  - 이벤트 기반
- Fetch
  - 프로미스 기반
  - IE지원X, 폴리필 필요
- Axios
  - 프로미스 기반

<br>
