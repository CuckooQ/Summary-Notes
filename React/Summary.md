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

- 정의
- 라이브러리명
- 컴포넌트 종류
- 형태
- URL ID 가져오기 방법
- URL QueryString 가져오기 방법

#### [17. Context](#Context)

- 정의
- 생성 방법
- 가져오기 방법
- 업데이트 방법
- displayName

#### [18. UI 에러 처리](#UI-에러-처리)

- 방법
- ErrorBoundary
- 포착 불가 에러

#### [19. Fragment](#Fragment)

- 정의
- 형태

#### [20. HOC](#HOC)

- 정의
- 목적
- 코딩룰

#### [21. Portal](#Portal)

- 정의
- 사용법
- 사용 케이스
- 특징

#### [22. 스타일링 라이브러리](#스타일링-라이브러리)

- CSS Module
- Classnames
- Styled Component
- React Shadow

#### [23. Profiler](#Profiler)

#### [24. 최적화](#최적화)

- Production Build
- Virtualizing Long List
- Rendering Optimization

#### [25. 리액트 프레임워크](#리액트-프레임워크)

- Create React App
- Next.JS
- Gatsby

#### [26.개발용 라이브러리](#개발용-라이브러리)

- npx
- esLint
- prettier
- husky
- lint-staged

#### [27. Hook](#Hook)

- 정의
- 코딩룰
- 종류

#### [28. Redux](#Redux)

- 정의
- Key Principle
- Action
- Reducer
- Store
- React-redux
- Redux Middleware
- Redux History
- Ducks Pattern
- Plugin
- 방법

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
  - 비동기

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
  - snapshot 반환
- componentDidUpdate(prevProps, prevState, snapshot)

### Unmounting

- componentWillUnmount()

### Error

- componentDidCatch(error, info)
  - 에러 정보를 서버로 전송하는 목적
  - 하위 컴포넌트의 에러가 발생하는 경우 호출
- getDerivedStateFromError(error
  - 에러로 state를 갱신해서 화면에 표시하는 목적
  - 하위 컴포넌트의 에러가 발생하는 경우 호출
  - 새로운 state 반환

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

## Context

### 정의

- React 컴포넌트 트리 전체에서 상태 관리 목적의 기능

### 생성 방법

- React.createContext함수 사용
- const Context = React.createContext({  
   &nbsp; &nbsp;state: value,  
   &nbsp; &nbsp;...  
  });
  export default Context;

### 가져오기 방법

#### Consumer

- Context.Provider컴포넌트로 사용할 컴포넌트를 감싸고, 사용할 컴포넌트 안에서 Context.Consumer 컴포넌트로 감싸서 해당 Context의 상태들을 공유하는 방법
- \<Context.Provider value={{...states}}\>  
  &nbsp; &nbsp;\<Component\>  
  \</Context.Provider\>  
  ...  
  export default function Component() {  
   &nbsp; &nbsp;return (  
   &nbsp; &nbsp; &nbsp; &nbsp;\<Context.Consumer\>  
   &nbsp; &nbsp; &nbsp; &nbsp;{(Context) => (  
   &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;...{Context...}  
   &nbsp; &nbsp; &nbsp; &nbsp;)}  
  &nbsp; &nbsp; &nbsp; &nbsp;\</Context.Consumer\>  
  &nbsp; &nbsp;)  
  }

#### Class Component

- 클래스 컴포넌트에서는 static contextType에 해당 Context를 지정하고 this.context에서 필요한 상태들을 가져와서 사용하는 방법
- import Context from "../contexts/Context";  
  ...  
  static contextType = Context;  
  ...  
  const {...} = this.context;

#### Function Component

- 함수 컴포넌트에서는 useContext훅을 사용하는 방법

### 업데이트 방법

- Context에 상태를 업데이트할 함수를 정의해서 사용

### displayName

- 개발자 도구에서의 Context 표시 이름

<br>

## UI 에러 처리

### 방법

최상위 컴포넌트를 ErrorBoundary컴포넌트로 감싸기

### Error Boundary

- 모든 하위 컴포넌트 트리 내에서 발생하는 JS에러를 기록하고 fallback UI를 표시하는 클래스 컴포넌트
- ```
  class ErrorBoundary extends React.Component {
    constructor(props) {
      super(props);
      this.state = {hasError: false};
    }
    static getDerivedStateFromError(error) {
      return {hasError: true};
    }
    componentDidCatch(error, info) {
      logErr(error, info);
    }
    render() {
      if(this.state.hasError) {
        return <ErrorComponent />
      }
      return this.props.children;
    }
  }
  ```

### 포착 불가 에러

- 이벤트 핸들러 에러
- 비동기 코드 에러
- 서버 사이드 렌더링 에러
- 에러 경계 자체에서 발생하는 에러

<br>

## Fragment

### 정의

- 그룹화 컴포넌트

### 형태

- \<React.Fragment\> ... \</React.Fragment\>
- <>...</>

<br>

## HOC

### 정의

- 컴포넌트를 매개변수로 받아서 특정 기능이 추가된 새 컴포넌트를 반환하는 순수 함수

### 목적

- 컴포넌트 로직 재사용
- 횡단 관심사 부분의 중복 방지

### 코딩룰

- with Prefix

<br>

## Portal

### 정의

- 부모 컴포넌트의 바깥에 있는 DOM노드로 자식 컴포넌트를 렌더링해주는 기능

### 사용법

- ReactDOM.createPortal(child, container) 사용
- child: 렌더링할 자식 컴포넌트
- container: 부모 컴포넌트 바깥에 있는 DOM 노드

### 사용 케이스

- root 요소 밖에 모달 창 컴포넌트 렌더링

### 특징

- 이벤트 버블링
  - 포탈의 위치에 관계없이 포탈에서 발생한 이벤트가 상위로 전파되는 특징

<br>

## 스타일링 라이브러리

### CSS Module

#### 정의

- CSS파일에 선언한 클래스 이름들을 유니크하게 만드는 라이브러리

#### 확장자

- .module.css

#### 예시

- import styles from "./..module.css;  
  \<component className={styles["className"]} />  
  \<component className={styles.className} />

### Classnames

#### 정의

- 복수의 클래스명 번들 라이브러리

#### 예시

- import classNames from "classnames";  
  <component className={classNames("className1", {className2: state})}>

### Styled Components

#### 정의

- css를 개별적으로 사용하는 기존 방식과 달리, 전역적 중첩을 발생시키지 않도록 컴포넌트에서 스타일을 지정할 수 있는 라이브러리

#### 예시

- import styled from "styled-components";  
  const StyledComponent = styled.component\`  
   &nbsp; &nbsp;...  
  \`;  
  function Component() {  
   &nbsp; &nbsp;return \<StyledComponent>  
  &nbsp; &nbsp;...  
   &nbsp; &nbsp;\</StyledComponent>  
  }

### React Shadow

- 스타일 캡슐화 목적의 Shadow DOM을 이용한 라이브러리

<br>

## Profiler

- 리액트 애플리케이션이 렌더링하는 빈도와 비용을 측정하는 기능

<br>

## 최적화

### Production Build

- 앱을 배포할 경우의 빌드
- 개발 모드보다 더 빠르고 작게 빌드

### Virtualizing Long List

#### 최적화 방법

- 긴 목록을 렌더링하는 경우 windowing 라이브러리 사용을 통해 최적화

#### 종류

- react-window
- react-virtualized

### Rendering Optimization

- 조건에 따른 형태의 변경의 경우 태그를 변경하는 것이 아닌, 클래스 이름을 변경해서 스타일 변경
- 리스트의 목록의 key속성에 ID 설정
- 클래스 컴포넌트 사용의 경우 React.Component가 아닌 React.PureComponent 상속
- 컴포넌트 이벤트 함수는 외부에 개별적으로 정의, useCallback 사용

<br>

## 리액트 프레임워크

- Create React App
  - CSR
- Next.JS
  - SSR
- Gatsby
  - Static Site

<br>

## 개발용 라이브러리

### npx

- node package runner
- npm >5.2.0

### esLint

- 코딩 스타일 교정 라이브러리
- .eslintrc
  - esLint 설정 파일

### prettier

- 코드 포맷 교정 라이브러리
- .prettierrc
  - prettier 설정 파일

### husky

- Githook 제어 라이브러리

### lint-staged

- Git Staged 상태 파일 대상의 명령어 실행 라이브러리
- .lintstagedrc
  - lint-staged 설정 파일

<br>

## Hook

### 정의

- 함수 컴포넌트에서 상태 관련 로직 재활용 목적의 함수

### 코딩룰

- use Prefix

### 종류

#### useState

- state 기능 제공 훅
- const [state, setState] = useState(initValue);

#### useEffect

- 컴포넌트가 렌더링될 때마다 특정 작업 실행 목적의 훅
- componentDidMount, componentDidUpdate, componentWillUnmount 생명주기 구현 가능
- useEffect(() =>  
   &nbsp; &nbsp;componentDidMount | componentWillUpdate Action  
  &nbsp; &nbsp;return () => {componentWillUnmount Action}, [states])

#### useReducer

- 복잡한 상태 관리 목적의 useState 대체 훅
- const [state, dispatch] = useReducer(reducer, initValue);

#### useCallback

- 최적화 목적으로 지정한 상태들의 변화가 발생했을 경우에만 특정 처리를 실행하는 함수를 반환하는 훅
- const method = useCallback(() => {...}, [states]);

#### useMemo

- 최적화 목적으로 지정한 상태들의 변화가 발생했을 경우에만 특정 처리를 실행한 값을 반환하는 훅
- const value = useMemo(() => {...}, [states]);

#### useRef

- ref 생성 훅
- const ref = useRef();

#### useHistory

- history 반환 훅
- const history = useHistory();

#### useParams

- URL QueryString 반환 훅
- const params = useParams();

#### Custom Hook

- 직접 작성한 훅

<br>

## Redux

### 정의

- 상태 관리 라이브러리

### Key Principle

- Single Source Of Truth
- State is read-only
- Changes are made with Pure Function

### Action

#### 정의

- Store의 상태를 변경하는 객체

#### 형식

- {type: Type, ...params}

#### Action creator

- 액션을 생성하는 함수

### Reducer

#### 정의

- 액션을 받아서 액션에 따라 상태를 업데이트하는 불변의 순수 함수

#### 형식

- ```
  function reducer(state = initState, action) {
    switch(action.type) {
      case ActionName: {
        const newState = {...state}
        ...
        return newState;
      }
      ...
    }
    return state;
  }
  ```

### Store

#### 정의

- 앱의 모든 상태 트리를 갖는 객체

#### 특징

- 기본 단일 스토어

#### 생성 방법

- createStore(reducer, preloadState, enhancer)함수 사용
- enhancer
  - middlewares

#### 리듀서 합성 방법

- combineReducers({reducers})함수 사용

#### 상태 가져오기 방법

- getState()함수 사용

#### 액션 호출 방법

- dispatch(actionCreator(params))함수 사용

#### 상태 변화에 따른 리스너 등록

- subscribe(listener)함수 사용

#### 등록 방법

- ReduxContext 생성
- index.js의 App컴포넌트를 ReduxContext.Provider 컴포넌트로 감싸기
- ReduxContext.Provider의 value속성에 store값 지정

### React-redux

#### 정의

- redux 편의 기능 추가 라이브러리

#### 등록 방법

- index.js의 App컴포넌트를 Provider컴포넌트로 감싸기
- Provider컴포넌트의 store속성에 store값 지정

#### 컨테이너 작성 방법

- connect HOC 사용
- useSelector,
  useDispatch,
  useCallback 사용
  - const state = useSelector((state) => state.reducer);
  - const dispatch = useDispatch();
  - const func = useCallback((params) => dispatch(actionCreator(params)), [dispatch]);

### Redux Middleware

#### 정의

- dispatch의 앞/뒤에서 동작하는 미들웨어

#### 설정 방법

- createStore함수의 enhancer로서 applyMiddleware(middlewares) 설정

#### Redux Saga

- 사이드 이펙트 지원 미들웨어 라이브러리
- 데이터 요청, 비동기 작업, 브라우저 캐시와 같이 순수하지 않은 작업 처리
- effect

  - all([sagas])
    - 사가 등록
  - takeEvery(actionType, generatorFunction)
    - 사가에서 해당 액션 타입에 따른 사이드 이펙트 설정
  - call(asyncFunction(params))
    - 비동기 작업 실행
  - put(actionCreator(params))
    - 액션 호출

- 작성 방법
  - redux에 sagas 폴더 작성
  - sagas 폴더에 index.js 작성
  - index.js에 제너레이터 함수 rootSaga 작성
  - rootSaga의 내용으로 yield all([saga1(), saga2(), ...]); 설정
  - store.js에 sagaMiddleware.run(rootSaga) 설정

#### Redux Thunk

- 비동기 처리 지원 미들웨어 라이브러리

### Redux History

#### 설정 방법

- redux 폴더에 history.js 작성
- history.js에 createBrowserHistory함수로 history 정의
- reducer의 combineReducers({router: connectRouter(history)}) 설정
- store의 creatStore의 applyMiddleware함수의 매개변수로 routerMiddleware(histroy) 설정

### Ducks Pattern

#### 정의

- 리덕스 아키텍처 패턴

#### 원칙

- reducer함수는 export default한다
- action creator함수는 export한다
- action-type은 appName-reducerName/ACTION_TYPE형태로 작성한다

#### 작성 방법

- 리듀서를 modules폴더에 하나의 모듈로서 작성
- modules폴더의 index.js에 루트 리듀서 작성
- modules폴더의 각 리듀서에는 해당 리듀서에서 사용할 액션 타입, 액션 생성자도 같이 정의
- 리듀서 함수명은 reducer로 작성

#### 디렉토리

- redux
  - modules
    - index.js
    - reducerName.js
    - ...
  - sagas
    - index.js
    - sagaName.js
    - ...
  - history.js
  - store.js

### Plugin

- redux-devtools
  - 리덕스 상태와 액션의 흐름을 개발자 모드에서 확인할 수 있는 플러그인

### 방법

#### Redux Store 인증 토큰 다루는 방법

- services폴더에 브라우저에서 토큰을 가져오는 함수 추가
- store.js에서 토큰을 가져오는 함수 실행
- store.js에서 가져온 토큰을 createStore의 initValue 매개변수로서 {auth: {...authInitState, token}}으로 설정

#### Redux Saga 로그아웃 처리 방법

- 로그아웃 API 실행
- 토큰 제거
- 로그인 화면 이동

<br>
