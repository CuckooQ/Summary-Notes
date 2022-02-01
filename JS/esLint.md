# ESLint

<br>

## 목차

#### [1. 정의](#정의)

#### [2. 형식](#형식)

#### [3. 설정 방법](#설정-방법)

#### [4. 설정 우선순위](#설정-우선순위)

#### [5. 설정 항목](#설정-항목)

<br>

---

<br>

## 정의

- 정해진 규칙에 따라 자동으로 코드 포맷팅과 퀄리티를 교정해주는 린터 

<br>

## 형식

- 라이브러리
- 익스텐션

<br>

## 설정 방법

### 라이브러리

- .eslintrc.js에서 설정
- package.json의 eslintConfig에서 설정

### 익스텐션

- 설정에서 확장 > ESLint에서 설정 

<br>

## 설정 우선순위

1. .eslintrc.js
2. eslintConfig (.eslintrc.js가 존재하는 경우 비활성화)
3. settings.json (익스텐션 설정)

<br>

## 설정 항목 

### root

- .eslintrc 루트 파일 사용 여부
- boolean
- false일 경우 내 PC의 root 디렉토리까지 .esLintrc 파일을 찾는다 

### env

- 환경 설정
- {}
- 웹 환경
  - browser: true
- node 환경
  - node: true
- es6, es2017 ~ es2021
  - es****: true

### extends

- ESLint 룰 설정이 저장되어 있는 외부 파일 사용 설정
- []

### parser

- 각 파일을 검사할 파서 
- string
- 타입스크립트 파서 @typescript-eslint/parser

### parserOptions

- 자바스크립트 언어 옵션 설정
- {}

#### ecmaVersion

- 사용할 ECMAScript 버전 설정
- number
- 5 (default)

#### ecmaFeatures

- ECMAScript 언어 확장 기능 설정
- globalReturn
  - 전역 스코프 사용 여부
- impliedStric
  - strict mode 사용 여부
- jsx
  - JSX 사용 여부

#### sourceType

- 파서의 export 형태 설정
- script (default)
- module

### plugins

- []

#### eslint-config-airbnb-base

- 에어비엔비 린트 플러그인

#### eslint-config-next

- Next.js 전용 린트 플러그인

#### eslint-plugin-react

- 리액트 전용 플러그인

#### eslint-plugin-prettier

- 린트 위에 사용할 프리티어 플러그인

#### eslint-config-prettier

- 중복되는 프리티어 룰을 린트 설정에서 제외하는 플러그인

#### @typescript-eslint/eslint-plugin

- 타입스크립트 전용 플러그인

### rules

- ESLint 룰 직접 설정
- 자동 설정된 룰 중에 특정 룰을 비활성화하거나 특정 룰을 변경하는 등의 설정
- react/prop-types
  - 리액트 린트 환경에서 propTypes의 props 타입체크 처리 여부 
  - 0 / 1
- @typescript-eslint/explicit-module-boundary-types
  - 타입스크립트 린트 환경에서 function return 타입 명시 여부 
  - 0 / 1
- @typescript-eslint/no-empty-interface
  - 타입스크립트 린트 환경에서 빈 인터페이스 선언 금지 여부
  - 0 / 1
- @typescript-eslint/ban-ts-comment
  - 타입스크립트 린트 환경에서 @ts-<directive> 주석 금지 여부
  - 0 / 1
- @typescript-eslint/no-empty-function
  - 타입스크립트 린트 환경에서 빈 함수 선언 금지 여부
  - 0 / 1
- @typescript-eslint/ban-types
  - 타입스크립트 린트 환경에서 사용되는 특정 타입의 금지 여부
  - 0 / 1
- no-empty-function
  - 빈 함수 선언 금지 여부
  - 0 / 1
- prettier/prettier: ['error', {endOfLine: 'auto'}]
  - Delete 'CR' eslint (prettier/prettier) ESLint 에러 해결

<br>
