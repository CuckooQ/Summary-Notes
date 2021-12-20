# Security

<br>

## 목차

#### [1. 보안 방법](#보안-방법)

#### [2. 공격 방법](#공격-방법)

- XSS
- CSRF
- Clickjacking
- SQL Inection
- Code Injection
- HTTP Header Injection

<br>

---

<br>

## 보안 방법

### CSP 헤더 사용

- 프론트엔드 보안의 기본
- XSS, Clickjacking, Injection Attack 방어

### X-XSS-Protection:1;mode=block 헤더 사용

- 악성 코드 입력 방어

### X-Frame-options:deny 헤더 사용

- Iframe Embedding 방어

### Referrer-Policy:no-referrer 헤더 사용

- referer헤더의 세션 토큰이나 사용자 ID 유출 방지

### Access-Control-Allow-Origin:\* 금지

### 최신 디펜던시 유지

<br>

## 공격 방법

### XSS

- Cross Site Scripting
- 악의적인 스크립트 주입 공격

### CSRF

- Cross Site Request Forgery
- 사용자의 의도와 무관하게 공격자의 요청을 실행하게 하는 공격

### Clickjacking

- 투명 버튼이나 링크를 웹페이지에 숨겨서 의도하지 않은 콘텐츠에 접근하게 하는 공격

### SQL Injection

### Code Injection

### HTTP Header Inection

<br>
