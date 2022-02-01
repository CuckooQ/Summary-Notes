# Prettier

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

- 정해진 규칙에 따라 자동으로 코드 스타일을 정리해주는 포맷터 

<br>

## 형식

- 라이브러리
- 익스텐션

<br>

## 설정 방법

### 라이브러리

- .prettierrc에서 설정

### 익스텐션

- 설정에서 Javascript Format 내장 설정의 비활성화
- 설정에서 확장 > Prettier에서 설정 

<br>

## 설정 우선순위

1. .prettierrc
2. .editorconfig
3. settings.json (익스텐션 설정)

<br>

## 설정 항목 

### singleQuote

- 큰 따옴표의 작은 따옴표 변환 여부  
- boolean

### parser

- 사용할 파서 지정
- 타입스크릡트 사용의 경우 'typescript' 지정

### semi

- 문장 뒤 세미콜론 여부
- boolean

### useTabs

- 탭이 있는 줄의 들여쓰기 여부
- boolean

### tabWidth

- 탭을 눌렀을 때의 띄어쓰기 너비
- number

### trailingComma

- 객체, 배열, 함수 등의 후행에 쉼표 제어
- none
- es5
- all

### printWidth

- 한 줄 내 최대 길이
- number

### arrowParens

- 단독 화살표 함수의 매개 변수 주위 괄호 자동 붙힘 설정
- always
- avoid

### endOfLine

- 파일의 줄 끝 설정
- lf (line feed, \n)
- auto (OS별 처리 방식 다름)

<br>