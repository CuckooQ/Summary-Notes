# NextJS

<br>

## 목차

#### [1. 정의](#정의)

#### [2. 설치](#설치)

#### [3. 특징](#특징)

#### [4. Pre-rendering](#Pre-rendering)

- 정의
- 장점
- Hydration
- 종류
- Static Generation
- Server Side Rendering

#### [5. Layouting](#Layouting)

- 정의
- 형태

#### [6. 이미지](#이미지)

- 특징
- 사용 방법
- 리모트 이미지 사용 시 필수 설정

#### [7. 폰트](#폰트)

- 특징
- 설정 방법

#### [8. 스크립트](#스크립트)

- 사용 방법
- Script 속성

#### [9. 정적 파일](#정적-파일)

- 설정방법
- 사용 방법

#### [10. 환경 변수](#환경-변수)

- 설정 방법
- 형태

#### [11. 라우팅](#라우팅)

- 컨셉
- 설정 방법

#### [12. API 라우팅](#API-라우팅)

- 설정 방법
- 형태
- 미들웨어 설정
- Req
- Res

#### [13. 테스트](#테스트)

- Cypress
- Jest

#### [14. 배포 단계 확인](#배포-단계-확인)

#### [15. Vercel](#Vercel)

<br>

---

<br>

## 정의

- SSR지원 React 프레임워크

<br>

## 설치

- npx create-next-app --typescript

<br>

## 특징

- 모든 페이지 기본 Pre-rendering
- 동적 라우팅 지원

<br>

## Pre-rendering

### 정의

- 자바스크립트 파일이 로딩되기 전에 미리 HTML파일을 생성해서 보여주는 동작

### 장점

- UX 향상
- SEO 향상

### Hydration

- 프리렌더링된 후에 자바스크립트 파일을 로드하고 HTML과 연결해서 완전한 페이지 완성하는 동작

### 종류

- Static Generation
- Server Side Rendering

### Static Generation

- HTML파일을 빌드 시점에서 생성해서 요청 시 재사용하는 방법
- 페이지에서만 사용
- 서버 사이드 코드 직접 작성
- CDN 캐싱
- Server Side Rendering보다 추천되는 동작

#### Static Generation with No Data

- 외부 데이터 없이 페이지당 하나의 HTML파일을 정적 생성하는 방법

#### Static Generation with Data

- 외부 데이터를 가지고 HTML파일을 정적 생성하는 방법
- getStaticProps와 getStaticPath 모두 개발 모드에서는 모든 요청에서 불림
- 페이지 콘텐츠가 외부 데이터에 의존하는 시나리오

  - getStaticProps(context) 비동기 함수 사용
  - ```
    export async function getStaticProps(context) {
      ...
      return {
        props: {
          ...
        }
      };
    }
    ```
  - context
    - params
      - 동적 경로 객체
    - preview
      - 프리뷰 모드 여부
    - previewData
      - setPreviewData로 지정된 프리뷰 데이터
    - locale
      - 지역 문자열
    - locales
      - 지역 문자열 배열
    - defaultLocale
      - 초기 지역 문자열
  - return

    - props
    - revalidate
      - 갱신 주기를 의미하는 초 단위의 시간
    - notFound
      - NOT FOUND 여부
    - redirect
      - {destination: string, permanent: boolean}

  - ISR
    - Incremental Static Regeneration
    - 일정 주기마다 데이터의 최신 여부를 검사하고 업데이트된 데이터로 페이지를 재생성하는 방법
    - getStaticProps의 반환값에서 revalidate속성 지정

- 페이지 경로가 외부 데이터에 외존하는 시나리오

  - getStaticpaths 비동기 함수 사용
  - ```
    export async function getStaticPaths() {
      ...
      return {
        paths: [{
          params: {...}
        }],
        fallback: boolean | "blocking"
      };
    }
    ```
  - return
    - paths
      - 다이나믹 라우팅 경로 배열
      - 다이나믹라우트 키의 속성과 값 필요
    - fallback
      - false
        - paths로 생성되지 않은 경로는 404 페이지 표시
      - true
        - paths로 생성되지 않은 경로는 대체 페이지 표시
        - router.isFallback이 true인 경우의 대체 페이지 생성 필요
        - 웹 크롤러에서 대체 페이지는 제공X
        - 데이터 의존이 많은 정적 페이지에서 사용
      - 'blocking'

### Server Side Rendering

- HTML파일을 모든 요청시에 생성하고 사용하는 방법
- 페이지에서만 사용
- 서버 사이드 코드 직접 작성
- getServerSIdeProps 비동기 함수 사용
- ```
  export async function getServerSideProps(context) {
    const res = await fetch(...);
    const data = await res.json();
    return {props: {data}};
  }
  ```
- context
  - params
    - 동적 경로 객체
  - preview
    - 프리뷰 모드 여부
  - previewData
    - setPreviewData로 지정된 프리뷰 데이터
  - locale
    - 지역 문자열
  - locales
    - 지역 문자열 배열
  - defaultLocale
    - 초기 지역 문자열
  - req
    - HTTP 요청 객체
  - res
    - HTTP 응답 객체
  - query
    - 쿼리 객체
  - resolveUrl
    - 정규화된 요청 URL
- return
  - props
  - notFound
    - NOT FOUND 여부
  - redirect
    - {destination: string, permanent: boolean}

<br>

## Layouting

### 정의

- 전체 애플리케이션에서 공통적으로 사용하는 레이아웃를 개별적으로 컴포넌트로 구현해서 사용하는 방법

### 형태

- ```
  // components/Layout.js
  import NavBar from "./NavBar";
  import Footer from "./Footer";

  export deafult function Layout({children}) {
    return (
      <>
        <NavBar />
        <main>{children}</main>
        <Footer />
      </NavBar>
    )
  }

  // pages/_app.js
  import Layout from "../components/Layout";

  export default function MyApp({Component, pageProps}) {
    return (
      <Layout>
        <Component { ..pageProps} />
      </Layout>
    )
  }

  ```

<br>

## 이미지

### 특징

- Improved Performance
- Visual Stability
- Faster Page Loads (Image Lazy Loads)
- Asset Flexibility

### 사용 방법

#### Local Images

```
import Image from "next/image";
import localImage from "../public/...png";

function Component() {
  return (
    <>
      <Image
        src={localImage}
        alt="..."
        placeholder="blur"
      />
    </Image>
  );
}
```

#### Remote Images

```
import Image from "next/image";

function Component() {
  return (
    <>
      <Image
        src="...png"
        alt="..."
        placeholder="blur"
        width={...}
        height={...}
      />
    </Image>
  );
}
```

### 리모트 이미지 사용 시 필수 설정

- next.config.js에서 images 속성 설정

```
module.exports = {
  images: {
    domains: ["...", ...];
  }
}
```

<br>

## 폰트

### 특징

- 최적화 기능 내장

### 설정 방법

```
// pages/index.js
import Head from "next/head";

export default function IndexPage() {
  return (
    <div>
      <Head>
        <link
          href="fontURL"
          rel="stylesheet"
        />
      </Head>
    </div>
  );
}

```

<br>

## 스크립트

### 사용 방법

```
import Script from "next/script";

export default function Component() {
  return (
    <>
      <Script
        src="..."
        strategy="..."
      />
    </>
  );
}
```

### Script 속성

#### src

#### strategy

- afterInteractive (default)
  - 페이지 활성화 후 로드
  - 예시
    - 분석도구 스크립트
- beforeInteractive
  - 페이지 활성화 전 로드
  - 예시
    - 봇 디텍터 스크립트
    - 쿠키 동의 관리자 스크립트
- lazyOnload
  - 여유가 있는 시간에 로드
  - 예시
    - 채팅 지원 플러그인
    - 소셜 미디어 위젯

<br>

## 정적 파일

### 설정 방법

- public 루트에 저장

### 사용 방법

- "/..."

<br>

## 환경 변수

### 설정 방법

- .env.local에 설정

#### 브라우저 공개 변수

- NEXT_PUBLIC\_ Prefix 추가

### 형태

```
// .env.local
VARIABLES_A=valueA
VARIABLES_B=valueB
VARIABLES_C=valueC$VARIABLES_A
NEXT_PUBLIC_VARIABLES_D=valueD
...

// file
process.env.VARIABLES_A;
process.env.VARIABLES_B
process.env.NEXT_PUBLIC_VARIABLES_D

```

<br>

## 라우팅

### 컨셉

- 페이지 파일 기반 라우팅

### 설정 방법

#### 폴더

- pages

#### Index Routes

- /
  - pages/index.js
- routeName
  - pages/routeName.js

#### Nested Routes

- /mainRoute/nestedRoute
  - pages/mainRoute/nextedRoute.js

#### Dynamic Route Segments

- /routeName/:dynamicRouteName
  - pages/routeName/[dynamicRouteName].js
- /routeName/\*
  - pages/routeName/[...all].js
- 가져오기

  - ```
    import { useRouter } from "next/  router";

    function Component() {
      const router = useRouter();
      const { dynamicRouteName } = router. query;
    }
    ```

#### Linking

```
import Link from "next/link";

export default function Component() {
  return (
    <ul>
      <li>
        <Link href="/">
          <a>Home</a>
        </Link>
      </li>
      <li>
        <Link href="/routeA">
          <a>RouteA</a>
        </Link>
      </li>
       <li>
        <Link href="/routeB">
          <a>RouteB</a>
        </Link>
      </li>
      {list.map(({id, title}) => {
        <li key={id}>
          <Link
            href={{
              pathname: "/routeC/[id]",
              query: { id }
            }}
          >
            <a>{title}</a>
          </Link>
        </li>
      });}
    </ul>
  );
}
```

<br>

## API 라우팅

### 설정 방법

#### 폴더

- pages/api

#### Routes

- /api/apiName/
  - pages/api/apiName.js

#### Dynamic Routes

- api/apiName/[dynamicRouteName]
  - pages/api/apiName/[dynamicRouteName].js

### 형태

```
export default function handler(req, res) {
  const { id } = req.query;
  const { ... } = req.cookies;
  const { ... } = req.body;
  if(req.method === "METHOD_NAME") {
    res.status(statusNumber).json({attr: value});
  } else if(...) {
    ...
  }
  ...
}
```

### 미들웨어 설정

```
import Middleware from "middlewareLibrary";

const middleware = Middleware(...);

function runMiddleware(req, res, fn) {
  return new Promise((resolve, reject) => {
    fn(req, res, (result) => {
      if(result instanceof Error) {
        return reject(result);
      }

      return resolve(result);
    })
  });
}

async function handler(req, res) {
  await runMiddleware(req, res, middleware);

  res.json(...);
}

export default handler;
```

### Req

- query
- cookies
- body

### Res

- status(code)
- json(body)
- send(body)
  - HTTP 응답
  - body
    - string
    - object
    - buffer
- redirect(code, path)

<br>

## 테스트

### Cypress

#### 빠른 시작

- npx create-next-app --example with-cypress with-cypress-app

#### 사전 준비

- 프로덕션 모드에서의 서버 실행
  - npm run build
  - npm run start

### Jest

#### 빠른 시작

- npx create-next-app --example with-jest with-jest-app

<br>

## 배포 단계 확인

- 캐싱 사용하기
- 데이터베이스와 백엔드의 동일 지역 배포 확인
- JS 파일 최소화하기
- 로깅 확인
- 오류 처리 설정 확인
- 404 & 500 에러 페이지 제공하기
- 성능 측정 지원 확인
- Lighthouse를 이용해서 성능, 모범사례, 접근성, SEO 확인하기
- 지원 브라우저 및 기능 확인

<br>

## Vercel

- NextJS 개발사의 클라우드 플랫폼

<br>
