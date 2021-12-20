# Bundler

<br>

## 목차

#### [1. 정의](#정의)

#### [2. 부가 기능](#부가-기능)

#### [3. 종류](#종류)

#### [4. 공통 설정](#공통-설정)

- Browserlist
- Postcss
- Autoprefixer
- Babel

#### [5. Parcel](#Parcel)

- CLI
- 라이브러리

#### [6. Webpack](#Webpack)

- CLI
- 라이브러리
- 설정

<br>

---

<br>

## 정의

- 복수의 파일을 최소한의 파일들로 묶어주는 개발용 라이브러리

<br>

## 부가 기능

- 난독화  
  Obfuscation
- 최신 문법을 브라우저 호환 문법으로 번역  
  Transpilation
- 써드 파티 기능

<br>

## 종류

- Parcel
- Rollup
- Webpack

<br>

## 공통 설정

### Browserlist

#### 정의

- 지원 대상 브라우저 설정 라이브러리

#### 설정

- package.json의 browserlist속성에 배열 값으로 설정

### Postcss

#### 정의

- 필요한 플러그인들을 사용해서 CSS를 변환해주는 Post-Processor 라이브러리

#### 설정

- .postcssrc에서 es5로 설정

#### 버전 호환

- postcss ver8은 autoprefixer ver9와 호환

### Autoprfixer

- 최신 CSS를 브라우저 호환 문법으로 변환시켜주는 Postcss 플러그인 라이브러리

### Babel

#### 정의

- 최신 JS를 브라우저 호환 문법으로 변환시켜주는 Post-Processor 라이브러리

#### 설정

- .babelrc에서 es5로 설정

<br>

## Parcel

### CLI

#### 개발용 서버 시작

- parcel index.html

#### 에셋 빌드

- parcel build index.html

#### 옵션

- 결과 디렉토리
  - --out-dir dirName
  - dist (default)
- 포트
  - --port portNum
  - 1234 (default)
- 브라우저에서 열기
  - --open
- 파일 시스템 캐시 비활성화
  - --no-cache

### 라이브러리

#### parcel-plugin-static-files-copy

- 정적 파일을 빌드하지 않고 그대로 빌드 경로에 복사해주는 Parcel 개발용 라이브러리
- package.json의 staticFiles속성의 객체 값으로 staticPath: folderName 설정

<br>

## Webpack

### CLI

#### 개발용 서버 시작

- webpack-dev-server --mode development

#### 에셋 빌드

- webpack --mode production

### 라이브러리

#### webpack-cli

- webpack cli지원 개발용 라이브러리

#### webpack-dev-server

- webpack 개발서버 동작 지원 개발용 라이브러리

#### html-webpack-plugin

- 번들링 후에 JS파일을 지정한 HTML 파일과 병합을 지원하는 개발용 라이브러리

#### copy-webpack-plugin

- 정적 파일을 빌드하지 않고 빌드 경로에 복사해주는 개발용 라이브러리

#### css-loader

- css파일을 js가 읽을 수 있는 문자열로 변환해주는 개발용 라이브러리

#### style-loader

- css-loader가 변환한 문자열을 html파일의 style태그에 병합시켜주는 개발용 라이브러리

#### sass-loader

- sass파일을 css파일로 변환시켜주는 개발용 라이브러리

#### postcss-loader

- postcss 지원 개발용 라이브러리

### 설정

- webpack.config.js에서 es5로 설정

<br>
