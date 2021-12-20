# Jest

<br>

## 목차

#### [1. 정의](#정의)

#### [2. 지원 기능](#지원-기능)

- Test Matcher
- Test Snapshot
- Test Mock
- Test Runner
- Test Coverage

#### [3. 규칙](#규칙)

- 테스트명 작성 규칙
- 테스트 흐름 작성 규칙
- 테스트 입력 값 규칙

#### [4. Matcher](#Matcher)

- toBe
- toEqual
- not
- toBeNull
- toBeUndefined
- toBeDefined
- toBeTruthy
- toBeFalsy
- toBeGreaterThan
- toBeGreaterThanOrEqual
- toBeLessThan
- toBeLessThanOrEqual
- toMatch
- toContain
- toThrow

#### [5. 함수](#함수)

- test & it
- describe
- beforeEch
- afterEach
- beforeAll
- afterAll
- only & skip

<br>

---

<br>

## 정의

- JS 유닛 테스트 라이브러리

<br>

## 지원 기능

### Test Matcher

- 테스트 대상과 기대 결과를 비교해주는 기능

### Test Snapshot

- UI 컴포넌트를 렌더링해서 스크린샷을 찍고 기대 결과 참조 이미지와 비교해주는 기능

### Test Mock

- 테스트를 작성할 경우 해당 코드가 의존하는 부분을 대체하는 목을 지원하는 기능

### Test Runner

- 테스트 파일을 읽고 실행하고 결과를 특정 형식으로 출력해주는 기능

### Test Coverage

- 테스트가 충분한가를 나타내주는 기능

<br>

## 규칙

### 테스트명 작성 규칙

- 테스트 함수 이름
- 테스트 시나리오
- 테스트 예상 동작

### 테스트 흐름 작성 규칙

- AAA패턴
  - Arrange
  - Act
  - Assert

### 테스트 입력 값 규칙

- 간단한 값

<br>

## Matcher

### toBe

- 값 일치 확인

### toEqual

- 객체 일치 확인

### not

- 불일치 확인

### toBeNull

### toBeUndefined

### toBeDefined

### toBeTruthy

### toBeFalsy

### toBeGreaterThan

### toBeGreaterThanOrEqual

### toBeLessThan

### toBeLessThanOrEqual

### toMatch

- 정규식을 이용한 문자열 일치 확인

### toContain

- 이터레이터 객체의 특정 요소 포함 여부 확인

### toThrow

- 에러 발생 확인

<br>

## 함수

### test & it

- 테스트 함수

### describe

- 테스트 그룹화 함수

### beforeEach

- 동일 레벨 또는 하위 레벨의 각 테스트 함수가 실행되기 전에 반복적으로 실행하는 함수

### afterEach

- 동일 레벨 또는 하위 레벨의 각 테스트 함수가 실행된 후에 반복적으로 실행하는 함수

### beforeAll

- 동일 레벨 또는 하위 레벨의 모든 테스트 함수가 실행되기 전에 한 번만 실행하는 함수

### afterAll

- 동일 레벨 또는 하위 레벨의 모든 테스트 함수가 실행된 후에 한 번만 실행하는 함수

### only & skip

- 해당 테스트의 실행 / 스킵 설정 함수

<br>
