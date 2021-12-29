# Expression

<br>

## 목차

#### [1. Regular Expression](#Regular-Expression)

<br>

---

<br>

## Regular Expression

### 약어

- RegExp

### 역할

- String Search
- String Replace
- String Extract

### 형태

- /expression/flag

### 표현

#### ^str

- 줄 시작에 있는 str과 일치

#### str$

- 줄 끝에 있는 str과 일치

#### .str

- '.'위치의 임의의 문자와 str과 일치

#### str1 | str2

- str1이나 sr2와 일치

#### strchar?

- char가 없어도 str과 일치하거나 strchar와 일치

#### char{n}

- char가 n개 연속 일치

#### char{n, }

- char가 n개 이상 연속 일치

#### char{n,m}

- char가 n개 이상 m개 이하 연속 일치

#### str(?=char)

- char의 앞쪽이 str과 일치

#### (?=char)str

- char의 뒤 쪽이 str과 일치

#### \b

- 단어의 경계

#### \w

- '\_'이나 숫자나 알파벳과 일치하는 문자

#### \d

- 숫자

#### [0-9]

- 숫자

#### \s

- 스페이스나 탭

#### [a-z]

- 영문 소문자

#### [A-Z]

- 영문 대문자

#### [가-힣]

- 한글

### 플래그

#### g

- 복수의 결과를 배열로 반환

#### i

- 대소문자 구별 없이 검색한 결과 반환

#### m

- 각 행에서의 검색이 가능하도록 설정

### 함수

#### regex.exec(str)

- str에서 regex와 일치하는 결과를 배열로 반환

#### regex.test(str)

- str에서 regex와 일치 여부 반환

<br>
