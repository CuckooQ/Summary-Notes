# Typescript

<br>

## 목차

#### [1. 정의](#정의)

#### [2. 컴파일러](#컴파일러)

#### [3. 설정](#설정)

- 설정 파일
- 설정 요소

#### [4. 타입](#타입)

- 종류
- 특성
- 연산자

#### [5. 인터페이스](#인터페이스)

- 키워드
- 종류

#### [6. 추상 클래스](#추상-클래스)

- 키워드
- 예시

#### [7. 제네릭](#제네릭)

- 정의
- 타입 제약
- 예시

#### [8. 타입 별칭](#타입-별칭)

- 정의
- 키워드
- 예시

#### [9. 제어자](#제어자)

- 접근 제어자
- 기타 제어자

#### [10. 선택적 키워드](#선택적-키워드)

- 키워드
- 예시

#### [11. 유틸리티 타입](#유틸리티-타입)

#### [12. d.ts](#d.ts)

- 정의
- Ambient Declaration
- 경로
- 설정 조건
- 예시

<br>

---

<br>

## 정의

- Javascript Superset

<br>

## 컴파일러

- tsc

- tsc-watch
  - ts코드에 번경이 있을 경우 자동으로 컴파일해주고 JS로 실행시켜주는 라이브러리
  - nodemon의 TS버전

<br>

## 설정

### 설정 파일

- tsconfig.json

### 설정 요소

#### compilerOptions

- target
  - 컴파일 설정 ES버전
  - EX) es6
- module
  - 모듈 포맷
  - EX) commonJS
- strict
  - 엄격 모드 설정
  - true or false
- outDir
  - 아웃풋 디렉토리
  - EX) dist
- sourceMap
  - 소스맵 사용 여부
  - true or false
  - 프로덕션모드에서는 'false'로 자동 세팅
- typeRoots
  - 컴파일 목록에 자동으로 포함시킬 패키지 경로들의 배열

#### include

- 컴파일에 포함하는 파일 경로
- EX) src/\*\*/\*.ts

#### exclude

- 컴파일에 제외하는 파일 경로
- EX) ["node_modules"]

<br>

## 타입

### 종류

- boolean
- number
- string
- array
  - Array\<type\>
  - type[]
- tuple
  - 정해진 타입의 고정된 길이 배열
  - [type1, type2, ...]
- enum
  - 서로 연관된 상수들의 집합
- object
- null
- undefined
- void
- never
  - 절대 발생할 수 없는 타입을 나타내는 최하위 타입
- any
  - 모든 타입을 나타내는 최상위 타입
  - 지양해야 하는 타입
- unknown
  - any와 같은 최상위 타입
  - 지양해야 하는 타입
- Union
  - 2개 이상의 타입을 허용하는 타입
  - type1 | type2 | ...
- Intersection
  - 2개 이상의 타입을 조합하는 타입
  - type1 & type2 & ...

### 특성

#### 타입 지정

- 일반 변수, 매개 변수, 프로퍼티에 타입을 지정할 수 있는 특성
- prop: type

#### 타입 에러

- 지정한 타입과 대입한 값의 타입이 다른 경우 코드 작성 중에 에러를 캐치하는 특성

#### 타입 추론

- 타입 지정이 되어있지 않은 경우 타입을 추론하는 특성

#### 타입 단언

- 타입 지정이 되어 있지 않지만 컴파일 단계에서 지시가능한 타입을 단언하는 특성
- prop as type

#### 타입 가드

- 타입을 확인하고자 하는 변수를 매개변수로 설정하고 해당하는 타입과 일치 여부를 반환하는 함수
- 'param is type'을 반환 타입으로 지정
- const isNumber = (val: type): val is type {  
  &nbsp; &nbsp;return typeof val === "type"  
  }

### 연산자

- typeof
  - 해당하는 타입을 문자열로 반환하는 연산자
- keyof
  - 모든 프로퍼티명을 유니온으로 반환하는 연산자

<br>

## 인터페이스

### 키워드

- interface
- implements

### 종류

#### Common Interface

- interface Interface {  
  &nbsp; &nbsp;prop1: type1;  
  &nbsp; &nbsp;prop2: type2;  
  }

#### Function Interface

- Call Signature를 이용해서 구현하는 인터페이스
  - (pram: type1, ...): type2
- interface Method {  
  &nbsp; &nbsp;(pram: type1, ...): type2;  
  }

#### Constructor Interface

- Construct Signature를 이용해서 구현하는 인터페이스
  - new (param: type1, ...): type2
- interface Constructor {  
  &nbsp; &nbsp;new (param: type1, ...): type2;  
  }

#### Indexable Iterface

- Index Signature를 이용해서 구현하는 인터페이스
  - [key: type1, ...]: type2
- interface IndexableObj {  
  &nbsp; &nbsp;\[key: type1, ...\]: type2;  
  }

#### Extended Interface

- extends키워드로 다른 인터페이스를 상속한 인터페이스
- interface Interface extends Interface2 {  
  &nbsp; &nbsp;...  
  }

<br>

## 추상 클래스

### 키워드

- abstract
- extends

### 예시

- abstract class Class {  
   &nbsp; &nbsp;abstract prop: type;  
  }

<br>

## 제네릭

### 정의

- 재사용 목적으로 타입을 일반화하는 기능

### 타입 제약

- extends 키워드로 T 타입에 제약 추가 가능

### 예시

- interface Interface\<T\> {  
  &nbsp; &nbsp;prop: T  
  }
- interface Interface\<T extends type1 | type2 | ...\> {  
  &nbsp; &nbsp;prop: T  
  }

<br>

## 타입 별칭

### 정의

- 하나 이상의 타입을 조합해서 별칭을 부여하는 기능

### 키워드

- type

### 예시

- type Type = type1 | type2 | ...;

<br>

## 제어자

### 접근 제어자

- public
- protected
- private

### 기타 제어자

- static
- readonly

<br>

## 선택적 키워드

### 키워드

- ?

### 예시

- function func(param?: type) {  
   &nbsp; &nbsp;...  
  }
- class Class {  
   &nbsp; &nbsp;prop1?: type  
   &nbsp; &nbsp;prop2: type  
  }
- obj?.prop;

<br>

## 유틸리티 타입

### Partial\<Type\>

- 타입의 모든 속성들을 선택적인 속성들로 변경한 새로운 타입 반환

### Required\<Type\>

- 타입의 모든 속성들을 필수적인 속성들로 변경한 새로운 타입 반환

### Readonly\<Type\>

- 타입의 모든 속성들을 읽기 전용 속성들로 변경한 새로운 타입 반환

### Record\<Key, Type\>

- 타입으로 지정된 키 속성을 가진 새로운 타입 반환

### Pick\<Type, Key\>

- 타입에서 지정된 키만 선택된 속성으로 가진 새로운 타입 반환

### Omit\<Type, Key\>

- 타입에서 지정된 키만 제외한 나머지 속성들을 가진 새로운 타입 반환

### Exclude\<Type1, Type2\>

- 유니온 타입1에서 유니온 타입2를 제외한 새로운 유니온 타입 반환

### Extract\<Type1, Type2\>

- 유니온 타입1과 유니온 타입2의 교집합인 새로운 유니온 타입 반환

### NoNullable\<Type\>

- 타입에서 null과 undefined를 제외한 새로운 타입 반환

### Parameters\<Type\>

- 함수 타입의 매개변수를 가진 새로운 튜플 타입 반환
- Parameters\<typeof func\>

### ConstructorParameters\<Type\>

- 클래스 타입의 생성자의 매개변수를 가진 새로운 튜플 타입 반환
- ConstructorParameters\<typeof class\>

### ReturnType\<Type\>

- 함수 타입의 반환 타입을 가진 새로운 타입 반환
- ReturnType\<typeof func\>

<br>

## d.ts

### 정의

- 타입스크립트 선언 파일

### Ambient Declaration

- 자바스크립트 모듈을 타입스크립트에서 사용하기 위해 타입 정보를 별도의 파일로 선언하는 것

### 경로

- /@types/moduleName/index.d.ts

### 설정 조건

- tsconfig.json의 compilerOptions속성의 typeRoots 속성에 ["/node_modules/@types, "/@types] 값 설정

### 예시

- declare module 'moduleName' {  
  &nbsp; &nbsp; ...  
  }

<br>
