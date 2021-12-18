# React

<br>

## 목차

#### [1. Key Principle](#Key-Principle)

#### [2. Virtual DOM](#Virtual-DOM)

- 정의
- 동작 과정
- 특징

#### [3. React로 사고하기](#React로-사고하기)

- 구현 과정
- 컴포넌트 결정 기준
- 정적 버전 제작 방법
- 상태 결정 기준
- 상태 정의 위치 결정 과정

#### [4. JSX](#JSX)

- 정의
- 특징

#### [5. Dot Notation](#Dot-Notation)

- 정의
- 형태

#### [6. React Element](#React-Element)

- 정의
- 특징
- 생성 함수

#### [7. React DOM](#React-DOM)

- 정의
- Root DOM Node
- 함수

#### [8. Component](#Component)

- 정의
- 종류
- 상태 관리에 따른 분류
- 매개변수
- 반환값
- 특징
- 조건 렌더링
- 렌더링 방지 방법

#### [9. Props](#Props)

- 정의
- 기본값
- props.children
- 클래스 컴포넌트에서의 필수 설정

#### [10. State](#State)

- 정의
- 초기화 방법
- 업데이트 방법
- 특징
- 금지사항

#### [11. Life Cycle](#Life-Cycle)

- Initiation
- Mounting
- Updating
- Unmounting
- Error

#### [12. Event Handling](#Event-Handling)

- 코딩룰
- 브라우저 고유 이벤트와의 차이점
- this 처리 방법
- 에러 처리 방법

#### [13. Ref](#Ref)

- 정의
- 사용 이유
- 사용 케이스
- 생성 방법
- 가져오기 방법
- 전달 방법

#### [14. List](#List)

- 사용 방법
- key 특징

#### [15. Form](#Form)

- Form Elements
- 다중 입력 제어
- 제어 컴포넌트 Form 라이브러리
- 비제어 컴포넌트 Form 라이브러리

#### [16. React Router](#React-Router)

<br>

---

<br>

## Key Principle

- 필요한 경우에만 렌더링

<br>

## Virtual DOM

### 정의

- 실제 DOM이 필요한 경우에만 렌더링할 목적으로, 임시적으로 변경된 전체 화면을 렌더링해놓는 DOM

### 동작 과정

- 변경 발생
- Virtual DOM에 변경된 전체화면 렌더링
- DOM과 Virtual DOM 비교
- DOM의 변경된 부분만 렌더링

### 특징

- documentFragment을 이용해서 Virtual DOM과 같이 부분 렌더링이 가능하지만, Virtual DOM을 사용할 경우 수동으로 조작하지 않아도 된다
- 자바스크립트를 사용하기 때문에 일반 DOM처리보다 빠르다

<br>

## React로 사고하기

### 구현 과정

- UI의 컴포넌트 계층 구조 구분
- 정적 버전 제작
- 데이터 모델에 대한 최소한의 표현의 상태 결정
- 상태 정의 위치 결정
- 역방향 데이터 흐름 추가

### 컴포넌트 결정 기준

- SRP (Single Responsibility Principle)
- Minimum Unit
- A Piece of Data Model

### 정적 버전 제작 방법

- Top-Down
- Bottom-Up

### 상태 결정 기준

- DRY (Don't Repeat Yourself)
- Minimum
- Changeable

### 상태 정의 위치 결정 과정

- 상태 기반으로 렌더링하는 모든 컴포넌트 파악
- 공통 소유의 최상위 컴포넌트 파악하고 정의
  ( Lifting State )
- 적절한 컴포넌트가 존재하지 않을 경우, 공통 오너 컴포넌트를 상위 컴포넌트로 추가

<br>

## JSX

### 정의

- JavaScript XML
- JS Preprocessor
- JS 내부에 마크업 코드를 작성할 수 있는 JS 확장 문법 형식

### 특징

- XSS 방지
- {}안에 JS 코드 추가 가능

<br>

## Dot Notation

### 정의

- 하나의 모듈에서 복수의 컴포넌트를 export하는 경우 사용하는 기술

### 형태

- const Components = {  
   &nbsp; &nbsp;Component1: function(props) { <>...<> }  
   &nbsp; &nbsp;Component2: function(props) { <>...<> }  
  }  
  function NewComponent() {  
   &nbsp; &nbsp;return <Components.Component1 ...>  
  }

<br>

## React Element

### 정의

- 화면 표현의 기본 단위

### 특징

- 불변 객체

### 생성 함수

- React.createElement(type, [key: value, ...], [children])

#### Type

- Tag Name
- Component
- React Fragment

<br>

## React DOM

### 정의

- React Element와 일치하도록 DOM을 업데이트 해주는 라이브러리

### Root DOM Node

- React DOM에서 관리하는 모든 엘리먼트가 들어가는 태그

### 함수

- render(element, root)
  - React Element을 Root DOM Node에 렌더링하는 함수

<br>

## Component

### 정의

- 트리 구조의 재사용 가능한 개별 조각 함수나 클래스

### 종류

#### 함수 컴포넌트

- 클래스 컴포넌트보다 컴파일 최적화

#### 클래스 컴포넌트

### 상태 관리에 따른 분류

#### Controlled Component

- 엘리먼트가 사용하는 상태를 직접 관리하는 컴포넌트

#### Uncontrolled Component

- 엘리먼트가 사용하는 상태를 직접 관리하지 않고,
  엘리먼트의 참조만 소유한 컴포넌트

### 매개변수

- Props

### 반환값

- React Element

### 특징

- Composition
  - 컴포넌트 안에 다른 컴포넌트를 참조할 수 있는 특징
- Extraction
  - 컴포넌트를 작은 컴포넌트들로 나눌 수 있는 특징

### 조건 렌더링

- if else 사용
- && 연산자 사용
- ? 연산자 사용

### 렌더링 방지 방법

- null 반환

<br>

## Props

### 정의

- 읽기 전용의 컴포넌트 매개변수

### 기본값

- true

### props.children

#### 유형

- String
- Component
- JS Expression
- Function

#### 특징

- Boolean, Null, Undefined는 렌더링X

### 클래스 컴포넌트에서의 필수 설정

- constructor(props) {  
   &nbsp; &nbsp;super(props);  
  }

<br>

## State

### 정의

- 컴포넌트 안에서 관리되는 동적 데이터

### 초기화 방법

#### 클래스 컴포넌트

- 생성자 내에서 this.state 초기화

#### 함수 컴포넌트

- useState로 상태와 업데이트함수 초기화

### 업데이트 방법

#### 클래스 컴포넌트

- this.setState 사용

#### 함수 컴포넌트

- useState로 생성한 업데이트 함수 사용

### 특징

- 자식 컴포넌트의 props로 전달 가능

### 금지사항

- props를 이용한 업데이트 금지
- 다른 상태를 이용한 업데이트 금지
- 자신 컴포넌트의 props를 이용해서 전달 금지

<br>

## Life Cycle

### Initiation

- Constructor(props)
  - props & state 셋업

### Mounting

- ~~componentWillMount()~~
- getDerivedStateFromProps(nextProps, nextState)
  - 시간의 흐름에 따라 변화하는 props로 state 설정하는 생명 주기
  - 새로운 state 반환
- render()
- componentDidMount()

### Updating

- getDerivedStateFromProps(nextProps, nextState)
- ~~componentWillRecieveProps(nextProps)~~
- shouldComponentUpdate(nextProps, nextState)
  - 업데이트 여부 반환
- ~~componentWillUpdate(nextProps, nextState)~~
- render()
- getSnapshotBeforeUpdate(prevProps, prvState)
  - DOM 적용 전에 동작
  - snapshot 리턴
- componentDidUpdate(prevProps, prevState, snapshot)

### Unmounting

- componentWillUnmount()

### Error

- componentDidCatch(error, info)

<br>

## Event Handling

### 코딩룰

- camelCase
- 'on' Prefix

### 브라우저 고유 이벤트와의 차이점

- 정확히 일치X
- addEventListener 호출 필요X
- false 반환으로 동작 방지 불가

### this 처리 방법

- 생성자 안에서 this 바인딩

### 에러 처리 방법

- try catch 사용

<br>

## Ref

### 정의

- DOM 엘리먼트 접근 목적의 ID와 같은 유니크 속성

### 사용 이유

- React에서는 DOM 직접 제어 지양

### 사용 케이스

- 특정 input/textarea에 포커스 지정
- DOM 크기 가져오기
- 스크롤 위치 가져오기
- 스크롤 설정
- 캔버스에 그림 그리기
- 외부 라이브러리 사용

### 생성 방법

- React.createRef()

### 가져오기 방법

- this.ref.current....

### 전달 방법

- React.forwardRef()
- const Component = React.forwardRef((props, ref) => {  
   &nbsp; &nbsp;...  
  })  
  const ref = React.createRef();  
  \<Component ref={ref}\/>

<br>

## List

### 사용 방법

- map함수와 key속성 사용

### Key 특징

- 읽기 불가
- key는 id로 설정 필수
- key는 설정 없을 시 인덱스로 자동 설정
- 항목 순서 변경 가능한 경우, key에 인덱스 설정 금지
- key와 동일한 값의 사용이 필요할 경우, 다른 이름의 속성 추가로 대응

<br>

## Form

### Form Elements

#### input

- 속성
  - value
- 이벤트
  - onChange

#### textarea

- 속성
  - value
- 이벤트
  - onChange

#### select

- 속성
  - value
  - multiple
- 이벤트
  - onChange

#### option

- 속성
  - value
    - multiple이 true일 경우 배열로 설정

#### fieldset

#### legend

#### label

- input, textarea, select를 감싸는 형태로 사용

### 다중 입력 제어

- 이벤트 위임을 이용해서,여러 input 엘리먼트에 name속성을 추가하고, 상위 컴포넌트에서 event.target.name값을 통해 입력 제어

### 제어 컴포넌트 Form 라이브러리

- Formik
- redux-form

### 비제어 컴포넌트 Form 라이브러리

- react-hooks-form

<br>

## React Router

### 정의

- CSR에서의 라우팅 라이브러리

### 라이브러리명

- React Router DOM

### 컴포넌트 종류

#### BrowserRouter

- 라우터 최상위 컴포넌트

#### Switch

- Route 컴포넌트들을 감싸는 컴포넌트

#### Route

- 해당 링크와 컴포넌트를 연결시켜주는 라우터 컴포넌트
- 속성
  - path
  - component
  - exact
  - render

#### Redirect

- 리다이렉트를 발생시키는 페이지 이동 컴포넌트
- 속성
  - to

#### Link

- 리다이렉트를 발생시키지 않는 페이지 이동 컴포넌트
- 속성
  - to

#### withRouter

- 상위 컴포넌트의 props.location, history, match를 전달하는 리액트 라우터의 HOC
- withRouter(class component {...});

### 형태

- \<BrowserRouter\>  
  &nbsp; &nbsp;\<switch\>  
  &nbsp; &nbsp; &nbsp; &nbsp; \<Route path="..." component={...}\>  
  &nbsp; &nbsp; &nbsp; &nbsp; \<Route path="..." component={...}\>  
  &nbsp; &nbsp; &nbsp; &nbsp; ...  
  &nbsp; &nbsp;\</switch\>  
  \</BrowserRouter\>

### URL ID 가져오기 방법

- const {id} = props.match.params;

### URL QueryString 가져오기 방법

- Query-String라이브러리 사용
- const params = QueryString.parse(props.history.location.search);

<br>
