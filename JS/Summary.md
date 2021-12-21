# Javascript

<br>

## 목차

#### [1. 특징](#특징)

#### [2. 선언](#선언)

#### [3. 비구조화 할당](#비구조화-할당)

#### [4. 스코프](#스코프)

#### [5. 데이터 타입](#데이터-타입)

- Primitive Type
- Reference Type

#### [6. 리터럴](#리터럴)

#### [7. 조건문](#조건문)

#### [8. 반복문](#반복문)

#### [9. 함수](#함수)

- 구성
- 정의 방법
- 특징
- 종류
- 자주 사용되는 함수

#### [10. 연산자](#연산자)

#### [11. 키워드](#키워드)

#### [12. 예외](#예외)

#### [13. 코멘트](#코멘트)

#### [14. 프로미스](#프로미스)

- 정의
- Promise Executor
- 상태
- Rejection Events
- 함수
- Callback Hell
- Then Chaining
- async & await

#### [15. JSON](#JSON)

#### [16. 숫자](#숫자)

- 진수
- Numeric Separator
- Safe Number
- 함수
- 자릿수별 배열 생성 방법

#### [17. Math함수](#Math함수)

- 제곱 & 제곱근
- 로그
- 반올림
- 최대 & 최소
- 기타

#### [18. 날짜](#날짜)

- 구성 요소
- 생성 방법
- 함수
- 현재 날짜
- 경과시간 계산 방법

#### [19. 문자열](#문자열)

- 길이
- 인덱싱
- Template Literal
- Multi Line
- Escape Characters
- 함수

#### [20. 배열](#배열)

- 길이
- 인덱싱
- 생성 방법
- 병합
- 변경
- 함수

#### [21. 맵](#맵)

- 생성
- 길이
- 추가 & 변경
- 가져오기
- 삭제
- 존재 여부

#### [22. 셋](#셋)

- 생성
- 길이
- 추가
- 삭제
- 존재 여부

#### [23. 객체](#객체)

- 함수
- 비교
- Rest & Spread
- Optional Chaining

#### [24. 반복기](#반복기)

- Iteration Protocol
- Iterable
- Iterator

#### [25. 생성기](#생성기)

- 정의
- 형태

#### [26. 프록시](#프록시)

- 정의
- 형태
- 트랩
- Revocable Proxy

#### [27. Reflect](#Reflect)

- 정의
- 함수

#### [28. 프로토타입](#프로토타입)

#### [29. 모듈](#모듈)

- 정의
- 조건
- import & export

#### [30. 이벤트](#이벤트)

- Event Bubbling
- Event Capturing
- Event Delegation
- stopProgation
- preventDefault
- target
- currentTarget

#### [31. AJAX](#AJAX)

- 정의
- 특징

#### [32. Strict Mode](#Strict-Mode)

- 정의
- 적용 방법
- 특징

#### [33. 메모리 관리](#메로리-관리)

- 메모리 생존 주기
- 메모리 할당 유형
- Garbage Collection

#### [34. 프로세스 관리](#프로세스-관리)

- 이벤트 루프
- 런타임 모델
- Execution Context

<br>

---

<br>

## 특징

- JIT 컴파일 방식
- 일급함수 지원
  - 함수를 변수와 동일하게 다루는 함수
- 다중 패러다임 지원

  - 객체 지향형
  - 명령형
  - 함수형

- 프로토타입 기반 프로그래밍
  - 객체를 생성할 경우, 그 객체의 클래스를 정의하지 않는 것을 허용하는 프로그래밍 스타일
- 싱글 스레드
- 스크립트 언어

<br>

## 선언

- var
  - 재선언 가능
- let
- const

<br>

## 비구조화 할당

### 정의

- Destructuring Assignment
- 배열이나 객체의 속성을 해체해서 그 값을 개별 변수에 담을 수 있는 표현식

### 예시

- const {  
   name,  
   password,  
  } = req.data;
- const [line1, line2] = file.split("\n");

<br>

## 스코프

- Global Scope
- Block Scope
- Function Scope
- Lexical Scope
  - 호출 장소가 아닌, 선언 장소에 의해 유효 범위 결정

<br>

## 데이터 타입

### Primitive Type

- Boolean
- Number
- BigInt
- String
- Symbol
- Null
  - 빈 값
  - 하위호환 유지를 위해 typeof에서는 object로 출력
- Undefined
  - 할당되지 않은 값

### Reference Type

- Object
- Function

<br>

## 리터럴

- Boolean
  - True
  - False
- Integer
  - 2진수
  - 8진수
  - 10진수
  - 16진수
- Float
- String
- Array
- Object
- Regular Expression
- Enhanced Object Literals
  - const id = 1;  
    const pw = 1234;  
    const auth = {id, pw};

<br>

## 조건문

- if / else
- switch / case

<br>

## 반복문

- for
- for attr in obj
- for val of arr
- while
- do while
- continue
- break
- label

<br>

## 함수

### 구성

- name
- parameter
- content

### 정의 방법

- Function Expression
  - function foo(){}
- IIFE (Immediately Invoked Function Expression)
  - (function(){}());
- Function Declaration
  - const foo = function(){}

### 특징

- Hoisting
  - 함수가 실행되기 전에 함수 안에 있는 var변수나 함수 선언문을 유효 범위의 최상단으로 끌어올리는 특징
  - 실제 메모리 변화 없음
- Closure
  - 어떤 내부 함수를 감싸고 있는 외부 함수의 변수를 그 내부 함수에서 접근 가능한 특징
- Chaining
  - 함수를 연속적으로 붙여서 사용할 수 있는 특징
  - do1().do2().do3()...
- Default Paramters

### 종류

- Arrow Function
  - const foo = () => {}
  - this가 언제나 상위 스코프의 this 의미, 변경 불가
  - arguments 자동 정의X
  - bind, call, apply함수 사용 불가
  - 생성자로 사용 불가
- Annonymous Function
- Callback Function
  - 다른 함수의 매개변수로서 사용되는 함수
- Constructor Function
  - 객체를 생성하는 함수
- Variadic Arguments Function
  - 파라미터 개수가 정해져 있지 않은 함수
  - function (...args) {}

### 자주 사용되는 함수

- Timer
  - const timer = setTimeout(func, timeoutSec)
  - const interval = setInterval(func, timeoutSec)
  - clearTimeout(timer)
  - clearInterval(interval)
- Lodash
  - import \_ from "lodash"
  - \_.isEqual(obj1, obj2)
    - obj1객체와 obj2객체의 동일 여부 반환
  - \_.uniqBy(arr, attr)
    - arr의 객체 중 attr이 중복인 것을 제거한 배열 반환
  - \_.unionBy(arr1, arr2, attr)
    - arr1과 arr2 안의 객체 중 attr이 중복인 객체를 제거한 배열 반환
  - \_.find(arr, {attr: value})
    - arr의 객체 중 attr이 value인 객체 반환
  - \_.findIndex(arr, {attr: value})
    - arr의 객체 중 attr이 value인 객체의 인덱스 반환
  - \_.remove(arr, {attr: value})
    - arr의 객체 중 attr이 value인 객체 제거를 제거한 배열 반환.
  - \_.throttle(func, waitSec, options)
    - func를 waitSec동안 동시에 실행될 수 없도록 실행

<br>

## 연산자

- Arithmetic Operator
- Assignment Operator
- Bitwise Operator
- Comma Operator
- Comparison Operator
- Conditional Operator
- Group Operator
- Logical Operator
- New Operator
- Nullish Coalescing Operator ??
  - a ?? b  
    a가 null이나 undefined일 경우 b 반환
- Relational Operator
  - in Operator
    - prop or idx in obj
  - instanceof Operator
    - obj instanceof objectKind
- Spread Operator
- Square Operator \*\*
- String Operator
- Unary Operator

  - delete
  - typeof
  - void

<br>

## 키워드

- this
- super

<br>

## 예외

- try catch finally
- throw
- optional catch
  - catch의 매개변수를 사용하지 않는 경우 생략 가능한 특징

<br>

## 코멘트

- //
- /\*\*/

<br>

## 프로미스

- 정의
  - 비동기적으로 실행하는 작업의 결과를 나타내는 객체
- Promise Executor
  - (resolve, reject) => {}
- 상태
  - pending
  - fulfilled
  - rejected
  - settled
- Rejection Events
  - rejectionHandled
    - executor의 reject함수에 의해 처리된 후 발생하는 이벤트
  - unhandledrejection
    - 사용 가능한 reject함수가 없는 경우 발생하는 이벤트
- 함수
  - then
  - catch
  - finally
  - resolve
  - reject
  - all([promises])
    - 모든 프로미스를 이행하고 then함수 이행
    - 이행하는 중 거부된 프로미스가 발생한 경우 즉시 catch함수 이행
  - allSettled([promises])
    - 모든 프로미스를 이행하고 then함수 이행
    - 이행하는 중 거부된 프로미스가 발생한 경우 다른 프로미스를 모두 이행한 후에 catch함수 이행
  - race([promises])
    - 프로미스에서 하나라도 완료한 경우 then, catch함수 이행
  - any([...])
    - 프로미스에서 하나라도 성공한 경우 then함수 이행
    - 모든 프로미스가 실패한 경우 Aggregation Error 발생하고 catch함수 이행
- Callback Hell
  - 연속적으로 비동기처리를 하는 경우 콜백 함수들의 코드가 보기 어려워지는 특징
- Then Chaining
  - then함수 체이닝이 가능한 특징
  - Callback Hell 완화 가능
- async & await

<br>

## JSON

- parse("obj")
- stringify(obj)

<br>

## 숫자

### 진수

- 10진수
- 2진수
- 8진수
- 16진수

### Numeric Separator

- \_
- 숫자 사이에 삽입해서 가시적인 구분 효과를 주는 분리 기호

### Safe Number

- Number.MAX_SAFE_INTEGER
- Number.MIN_SAFE_INTEGER

### 함수

- Number(value)
- Number.isNaN(value)
- Number.isInteger(value)
- Number.parseInt(value)
- Number.parseFloat(value)
- num.toFixed(decimalPoint)
  - 소수점 decimalPoint까지 가지는 문자열 반환

### 자릿수별 배열 생성 방법

- num.toString().split("")

<br>

## Math함수

### 제곱 & 제곱근

- Math.pow(valuel, value2)
- Math.sqrt(value)
- Math.cbrt(value)

### 로그

- Math.log(value)
- Math.log10(value)
- Math.log2(value)

### 반올림

- Math.round(value)
- Math.ceil(value)
- Math.floor(value)

### 최대 & 최소

- Math.max(...)
- Math.min(...)

### 기타

- Math.abs(value)
  - 절대값 반환
- Math.trunc(value)
  - 정수값 반환
- Math.sign(value)
  - 부호 반환
- Math.random()
  - 0이상 1미만의 숫자 반환
  - 보안과 관련된 경우 window.crypto.getRandomValues() 사용

<br>

## 날짜

### 구성 요소

- Year
- Month
- Day
- Hour
- Min
- Sec
- MillSec

### 생성 방법

- new Date("YYYY-MM-DD hh:mm:ss")
- new Date(YYYY, MM, DD, hh, mm, ss)
- new Date(millSec)

### 함수

- Date.now()
  - 1970년 1월 1일 0시 0분 0초부터 현재까지의 경과시간 반환
  - 밀리 초 단위
- Date.parse("YYYY-MM-DD hh:mm:ss")
  - 1970년 1월 1일 0시 0분 0초부터 대상 시간까지의 경과 시간 반환
  - 밀리 초 단위
- Date.UTC(YYYY, MM, DD, hh, mm, ss)
  - 1970년 1월 1일 0시 0분 0초부터 대상 시간까지의 경과 시간 반환(UTC )
  - 밀리 초 단위

### 현재 날짜

- new Date()

### 경과시간 계산 방법

- const start = Date.now();  
  ...  
  const end = Date.now();  
  const elapsed = end - start;

<br>

## 문자열

### 길이

- length

### 인덱싱

- [idx]

### Template Literal

- \`${value}\`

### Multi Line

- 복수행의 문자열 정의 가능

### Escape Characters

- \\`
- \\"
- \\\\
- \\n
- \\r
- \\v
- \\t
- \\b

### 함수

#### 대소문자

- String.fromCharCode(n)
- 대문자 A-Z : 65 - 90
- 소문자 a-z : 97 - 112

#### 위치 찾기

- indexOf(str, num)
- lastIndexOf(str)
- search(regex or str)

#### 변환

- replace(regex or str, str)
- replaceAll(str1, str2)
- toUpperCase()
- toLowerCase()

#### 잘라내기

- slice(startIdx, endIdx)
- substring(startIdx, endIdx)
- substr(startIdx, length)
- trim()
- trimStart()
- trimLeft()
- trimEnd()
- trimRight()

#### 붙이기

- concat(...)
- padStart(num, num or str)
  - num-1개수의 num이나 str을 시작에 붙이기
- padEnd(num, num or str)
  - num-1개수의 num이나 str을 끝에 붙이기

#### 배열 반환

- split(str)
- match(regex)

#### 문자 반환

- charAt(idx)

#### 이터레이터 반환

- matchAll(regex)

<br>

## 배열

### 길이

- length

### 인덱싱

- [idx]

### 생성 방법

- new Array(...)
- Array(...)
- [...]

### 병합

- newArr = [...arr1, ...arr2]

### 변경

- [arr[i], arr[j]] = [arr[j], arr[i]]

### 함수

#### 배열 여부

- isArray()

#### 요소 찾기

- indexOf(val, idx)
- lastIndexOf(val, idx)
- find(callback)
- findIndex(callback)

#### 생성

- Array.from({length: len}, () => { return value })
- Array.of(values)

#### 삽입

- push(arr)
- unshift(arr)
- concat(arr)

#### 변경

- fill(value, startIdx, endIdx)
- flat(num)
  - 다중 배열을 num횟수만큼 펼쳐서 하위 배열 반환
- flatMap(callback)
  - map과 flat을 섞은 기능

#### 제거

- pop()
- shift()
- splice(startIdx, length, arr)
  - startIdx 인덱스부터 length길이만큼 제거하고 arr를 붙인 배열 반환
- slice(startIdx, endIdx)
  - startIdx 인덱스부터 endIdx-1 인덱스까지 자른 배열 반환

#### 순서 변경

- reverse()
- sort(callback)

#### 조건 일치 여부

- includes(val, idx)
- every(callback)
- som(callback)

#### 필터링

- forEach(callback)
- filter(callback)
- map(callback)

#### 문자열 반환

- join(str)

#### 이터레이터 반환

- entries()
- keys()
- values()

#### 축적 값 반환

- reduce((acc, cur, idx, arr) => expression, initValue)
- reduceRight((acc, cur, idx, arr) => expression, initValue)

<br>

## 맵

### 생성

- new Map()

### 길이

- size

### 추가 & 변경

- set(key, val)

### 가져오기

- get(key)

### 삭제

- delete(key)

### 존재 여부

- has(key)

<br>

## 셋

### 생성

- new Set()

### 길이

- size

### 추가

- add(val)

### 삭제

- delete(val)

### 존재 여부

- has(val)

<br>

## 객체

### 함수

- Object.keys(obj)
- Object.values(obj)
- Object.entries(obj)
- Object.fromEntries([...[prop, val]])
  - 2차원 배열을 객체로 변환
- Object.assign(obj1, obj2)
  - obj1객체에 obj2객체를 병합한 객체 반환

### 비교

- lodash함수 \_.isEqual(obj1, obj2) 사용

### Rest & Spread

#### Rest

- {...obj} = {property: value, ...}

#### Spread

- obj = {property: value, ...obj}

### Optional Chaining

- obj?.property1?.property

<br>

## 반복기

### Iteration Protocol

#### Iterable Protocol

- 반복 가능한 객체를 나타내는 프로토콜

#### Iterator Protocol

- 반복 가능한 객체의 값을 시퀸스대로 처리하는 프로토콜

### Iterable

#### 정의

- 반복 가능한 객체

#### 조건

- 객체 내에 [Symbol.iterator](){ return iterator }함수 존재

### Iterator

#### 정의

- Iterable Object내에서 반복을 실행하는 반복기

#### 조건

- next함수 존재

#### next함수

- Iterator Result 객체를 반환하는 함수

#### Iterator Result

- {done: boolean, value: any} 객체
- 가장 마지막을 나타내는 경우 done은 true 상태로 반환
- done이 true로 반환된 이후에는 true로 계속 반환하거나 undefined 반환

<br>

## 생성기

### 정의

- iterable 객체를 생성하는 함수

### 형태

- function\* generator() {  
  &nbsp; &nbsp;yield val1;  
  &nbsp; &nbsp;yield val2;  
  &nbsp; &nbsp;...  
  }
- generator.next()

<br>

## 프록시

### 정의

- 어떤 객체의 기본적인 동작에 새로운 행동을 정의하기 위한 목적의, 실제 객체를 대신하는 객체

### 형태

- proxy = new Proxy(obj, handler)
- handler는 트랩을 가진 객체

### 트랩

- 프로퍼티에 접근할 수 있는 함수

#### get

- get: function(target, prop) {  
  &nbsp; &nbsp;...  
  }

#### set

- set: function(target, prop, value) {  
  &nbsp; &nbsp;...  
  }

#### has

- has: function(target, prop) {  
  &nbsp; &nbsp;...  
  }

### Revocable Proxy

#### 정의

- 폐기할 수 있는 프록시

#### 형태

- proxy = Proxy.revocable(target, handler)

#### 폐기

- revoke함수 사용

<br>

## Reflect

### 정의

- 명령을 가로챌 수 있는 함수를 제공하는 내장 객체

### 함수

- get(target, prop, receiver)
- set(target, prop, value, receiver)
- has(target, prop, receiver)

<br>

## 프로토타입

- 객체의 원형

<br>

## 모듈

### 정의

- 프로그램 기능 묶음의 단위

### 조건

- html 파일에서 script 태그의 type속성에 'module' 설정

### import & export

<br>

## 이벤트

### Event Bublling

- 요소의 이벤트가 요소의 상위 요소들까지 전달되는 현상

### Event Capturing

- 요소의 이벤트가 자식 요소들까지 전달되는 현상
- addEventListener함수의 매개변수중 options의 capture속성에 true로 설정

### Event Delegation

- 하위 요소들의 이벤트를 상위 요소에서 제어하는 방식

### stopProgation

- 이벤트 버블링 & 캡처링 방지 함수

### preventDefault

- 이벤트가 발생한 요소의 기본 동작 실행 방지 함수

### target

- 이벤트가 발생한 요소

### currentTarget

- 이벤트를 다루는 요소

<br>

## AJAX

### 정의

- Asynchronous Javascript And Xml
- 비동기적으로 서버와 클라이언트가 데이터를 교환할 수 있는 통신 방식

### 특징

- 전체 페이지를 갱신하지 않고 일부만 갱신 가능
- XML보다 JSON을 더 많이 사용

## Strict Mode

### 정의

- 자바스크립트 코드의 실행을 엄격하게 관리하는 모드

### 적용 방법

- 스크립트 파일 최상단에 'use strict' 추가

### 특징

- 최적화 용이
- 모듈과 클래스의 경우 자동 적용

<br>

## 메모리 관리

### 메모리 생존 주기

- 필요한 경우 할당
- 읽기, 쓰기
- 필요없어진 경우 해제

### 메모리 할당 유형

- 값 초기화
- 함수 호출

### Garbage Collection

#### 정의

- 메모리 관리 수행 프로세스

#### 특징

- 수동으로 메모리 해제 불가

#### 알고리즘

- 참조-세기 알고리즘
  - Reference-counting Algorithm
  - 더 이상 필요 없는 객체 = 아무도 참조하지 않는 객체
- 표시하고-쓸기 알고리즘
  - Mark-and-sweep Algorithm
  - 더 이상 필요 없는 객체 = 닿을 수 없는 객체

<br>

## 프로세스 관리

### 이벤트 루프

#### 정의

- 자바스크립트의 작업 루프

#### 기능

- 동시성 모델 지원

### 런타입 모델

#### Call Stack

- 작업을 쌓아놓는 영역
- 최대 허용치 존재
- 최대 허용치를 넘는 경우 'Maximum Size Exceeded' 에러 발생

#### Callback Queue

- 비동기 처리를 임시로 보관하는 영역
- 콜 스택이 비어있을 경우 처리를 콜백 큐에서 콜 스택으로 이동시키는 틱 발생

#### Memory Heap

- 객체들이 할당되는 메모리 영역

### Execution Context

#### 정의

- 자바스크립트 코드가 실행되는 작업

#### 특징

- 콜 스택에 저장

<br>
