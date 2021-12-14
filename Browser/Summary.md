# BROWSER

<br>

## 목차

#### [1. 웹페이지 로드 과정](#웹-페이지-로드-과정)

#### [2. 브라우저 구성 요소](#브라우저-구성-요소)

#### [3. 렌더링 엔진 동작 과정](#렌더링-엔진-동작-과정)

#### [4. 렌더링 엔진 동작 특징](#렌더링-엔진-동작-특징)

#### [5. 크로스 브라우징](#크로스-브라우징)

#### [6. 크로스 브라우징 방법](#크로스-브라우징-방법)

- [Graceful Degradation](#Graceful-Degradation)
- [Progressive Enhancement](#Progressive-Enhancement)

#### [7. 저장소](#저장소)

- [Cookie](#Cookie)
- [Local Storage](#Local-Storage)
- [Session Storage](#Session-Storage)

#### [8. 인증](#인증)

- [Token Authorization](#Token-Authorization)
- [JWT](#JWT)
- [Session Authorization](#Session-Authorization)

#### [9. 지연 로드](#지연-로드)

#### [10. 지연 로드 구현](#지연-로드-구현)

#### [11. 반응형 웹](#반응형-웹)

- [미디어 쿼리 문법](#미디어-쿼리-문법)
- [디바이스 크기](#디바이스-크기)

#### [12. 적응형 웹](#적응형-웹)

#### [13. 뷰포트](#뷰포트)

#### [14. SEO](#SEO)

<br>

---

<br>

## 웹 페이지 로드 과정

- Prompt to Unload
- Redirect
- DNS
- TCP Req & Res
- Load & Processing

<br>

## 브라우저 구성 요소

- UI
- Browser Engine
- Rendering Engine
- Network
- JS Translator
- UI Backend
- Data Storage

<br>

## 렌더링 엔진 동작 과정

- HTML & CSS & JS Parsing.
- DOM & CSSOM Converting.
- Render Tree Making using DOM & CSSOM.
- Render Tree Layouting.
- Render Tree Painting & Composition.

### **Render Tree Painting & Composition**

- 요소를 픽셀로 변환해서 레이어를 만들고, 여러 레이어를 합성하는 과정.

<br>

## 렌더링 엔진 동작 특징

- 점진적 실행.
- 렌더 트리 레이아우팅 단계가 실행되면, 렌더 트리 페인팅과 합성 단계도 반드시 실행.

<br>

## 크로스 브라우징

- 서비스가 지정한 여러 브라우저에서 올바르게 작동하게 하는 작업.

<br>

## 크로스 브라우징 방법

- Graceful Degradation
- Progressive Enhancement

### Graceful Degradation

- 최신 기술 환경에서 동작하도록 구현한 후에, 오래된 기술 환경에서 동작하도록 유사한 기능을 만들어 제공하는 방법.

### Progressive Enhancement

- 오래된 기술 환경에서 동작하도록 구현한 후에, 최신 기술 환경에서 더 나은 기술로 제공하는 방법.

<br>

## 저장소

- Cookie
- Web Storage
  - Session Storage
  - Local Storage

### Cookie

- 브라우저 로컬에서 관리.
- 같은 도메인의 서버로 자동 전송.
- 만료기한 지정 가능.
- 제한 용량 4kb.
- 문자열의 키와 값 데이터.
- getCookie(key)
- setCookie(key, value)
- 인증 정보 저장.  
  HttpOnly: True,  
  Secure: True,  
  SameSite: Strict,  
  Domain속성 등의 보안 설정 필요.

### Local Storage

- 브라우저 로컬에서 관리.
- 같은 도메인의 서버로 임의 전송.
- 만료기한 없음.
- 제한 용량 5mb.
- 문자열의 키와 값 데이터.
- sessionStorage.getItem(key)
- sessionStorage.setItem(key, value)

### Session Storage

- 서버에서 관리.
- 같은 도메인의 서버로 임의 전송.
- 탭을 닫거나 브라우저 종료 시 삭제.
- 제한 용량 5mb.
- 문자열의 키와 값 데이터.
- localStorage.getItem(key)
- localStorage.setItem(key, value)

<br>

## 인증

- Token Authorization
- Session Authorization

### Token Authorization

- 사용자가 인증하면 서버에서 토큰 정보를 발급한다.  
  이 때 토큰 정보에는 인증에 필요한 정보가 직접적으로 담겨 있다.  
  토큰 정보를 사용자에게 보내고 사용자는 토큰 정보를 클라이언트의 저장소에 저장하고 사용한다.  
  서버에서는 토큰 정보가 담긴 요청이 오는 경우, 토큰 정보가 유효한 지 판별한다.
- 토큰의 악의적 탈취가 발생하는 경우에 대비해서 토큰 파기 기능이나 Access / Refresh 토큰 구현 필요.
- JWT 인증 방식이 통상적.

### JWT

- Header
  - typ : 타입
  - alg : 해싱 알고리즘
- Payload
  - 클레임으로 지정하는, 토큰에 담을 데이터.
- Signature
  - 헤더와 페이로드를 base64 URL로 인코딩한 후에, 헤더에 규정한 해싱 알고리즘으로 서명한 값.
- 페이로드 내용은 디코딩될 수 있으므로 민감한 정보는 담지 않는다.

### Session Authorization

- 사용자가 인증하면 서버에서 세션 정보를 발급하고 서버의 저장소에 저장한다. <br>
  그리고 그 세션 정보를 사용자에게 보내고 사용자도 세션 정보를 클라이언트의 저장소에 저장하고 사용한다.<br>
  서버에서는 세션 정보가 담긴 요청이 오는 경우, 서버 저장소에 있는 세션 정보와 비교해서 유효한 세션 정보인지 판별한다.
- 인증에 필요한 정보가 직접적으로 담겨있지 않고 서버에서 관리하기 때문에 클라이언트에서의 변조 위험성이 적다.
- 서버에도 세션 정보를 저장하는 저장소가 필요하기 때문에 스케일 아웃/인에 영향을 줄 수 있다.

<br>

## 지연 로드

- 페이지 로딩 시점에 필요하지 않은 자원들의 로딩 시점을 지연시키는 기술.

<br>

## 지연 로드 구현

- 요소의 소스 URL을 src속성이 아닌 data-src속성에 지정.
- InteractionObserver API를 이용해서, 스크롤, 화면 크기 변경, 방향 전환 이벤트로 인해 뷰포트상에서 지정한 범위에 들어오는 경우를 캐치.
- data-src의 URL을 src속성의 값으로 지정.

<br>

## 반응형 웹

- 미디어 쿼리로 화면 크기를 확인해서 레잉아웃을 조절하는 웹.

### 미디어 쿼리 문법

- @media media-type (max-width: -) {<br>
  declaration<br>
  }

### 디바이스 크기

- mobileSm : 320px
- mobile : 600px
- tabletSm : 834px
- tablet : 1024px

<br>

## 적응형 웹

- 서버나 클라이언트에서 접속한 기기를 확인해서 기기에 맞는 템플릿을 조절하는 웹.

<br>

## 뷰포트

- 웹페이지가 사용자에게 보여지는 영역.

<br>

## SEO

- 웹 사이트의 페이지들을 웹 검색 크롤러가 잘 읽을 수 있도록 콘텐츠를 만들고 최적화하는 것.

<br>
