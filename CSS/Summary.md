# CSS

<br>

## 목차

#### [1. Rule Set](#Rule-Set)

#### [2. Selectors](#Selectors)

#### [3. Pseudo Classes](#Pseudo-Classes)

#### [4. Pseudo Elements](#Pseudo-Elements)

#### [5. Order of Priority](#Order-of-Priority)

#### [6. Inheritance](#Inheritance)

#### [7. Image](#Image)

- [비트맵](#비트맵)
- [벡터](#벡터)

#### [8. Color Unit](#Color-Unit)

#### [9. Size](#Size)

#### [10. Size Unit](#Size-Unit)

#### [11. Overflow](#Overflow)

#### [12. Opacity](#Opacity)

#### [13. Stack Level](#Stack-Level)

#### [14. Background](#Background)

#### [15. Transition](#Transition)

#### [16. Transform](#Transform)

#### [17. Perspective](#Perspective)

#### [18. Outline](#Outline)

#### [19. Text Style](#Text-Style)

- [폰트](#폰트)
- [텍스트 레이아웃](#텍스트-레이아웃)

#### [20. Box Model](#Box-Model)

#### [21. Placement](#Placement)

- [Float](#Float)
- [Position](#Position)
- [Centering](#Centering)

#### [22. Display](#Display)

#### [23. Layout](#Layout)

- [Grid](#Grid)
- [Flex Box](#Flex-Box)

<br>

## Rule Set

- selector {  
   declaration (property: value)  
  }

<br>

## Selectors

- Universal Selector (\*)
- Element Selector (El)
- Id Selector (#id)
- Class Selector (.class)
- Attribute Selector ([attr])
- Pseudo Class Selector (El:state)
- Pseudo Element Selector (El::state)
- Descendant Combinator (ElA ElB)
- Child Combinator (ElA > ElB)
- General Sibling Combinator (ElA ~ ElB)
- Adjacent Sibling Combinator (ElA + ElB)

<br>

## Pseudo Classes

- :active
- :hover
- :default
- :not(selector)
- :empty
- :only-of-type
- :only-child
- :first-child
- :first-of-type
- :last-child
- :last-of-type
- :nth-child(n)
- :nth-of-type(n)
- :nth-last-child(n)
- :nth-last-of-type(n)
- :lang(lang)
- :root
- :checked
- :focus
- :in-range
- :out-of-range
- :valid
- :invalid
- :enabled
- :disabled
- :required
- :optional
- :read-only
- :read-write
- :visited
- :link
- :target

<br>

## Pseudo Elements

- ::before
- ::after
- ::first-letter
- ::first-line
- ::placeholder
- ::selection

### content

- string
- image
- none

<br>

## Order of Priority

- !important
- Inline Style Attribute
- Id Selector
- Attribute, Class Selector, Pseudo Class Selector
- Element Selector, Pseudo Element Selector

<br>

## Inheritance

### 대상

- 대부분의 글자/문자 관련 속성.

### 강제 상속 방법

- inherit 값 사용.

<br>

## Image

### 종류

- 비트맵
- 벡터

### 비트맵

#### 정의

- 픽셀이 모여 만들어진 이미지

#### 다른 명칭

- 레스터 (Raster)

#### 장점

- 정교하고 다양한 색상 표현 가능.

### 단점

- 확대 / 축소 시 계단 현상, 품질 저하 발생.

#### 유스케이스

- 실제 사진

#### 확장자

- jpg (압축률)
- png (투명도)
- gif (복수 이미지 저장)
- webp (모두 대체 가능)
- ico (파비콘, 32px x 32px)

### 벡터

#### 정의

- 점, 선, 면, 색상으로 이루어진 이미지

#### 장점

- 확대 / 축소에 자유로움

#### 단점

- 정교한 이미지 표현 어려움

#### 유스케이스

- 아이콘
- 로고

#### 확장자

- svg

<br>

## Color Unit

- Hexadecimal Colors  
  #rrggbb
- RGB  
  rgb(r, g, b)
- RGBA  
  rgba(r, g, b, a)
- HSL  
  hsl(h, s, l)
- HSLA  
  hsla(h, s, l, a)

<br>

## Size

- width
- height
- inline-size
- block-size

<br>

## Size Unit

- px
- %
- em
- rem
- vw
- vh
- vmin
- vmax

<br>

## Overflow

### property

- overflow
- overflow-x
- overflow-y

### value

- auto
- visible
- hidden
- scroll

<br>

## Opacity

### property

- opacity

### value

- 0 ~ 1

<br>

## Stack Level

### Property

- z-index

### value

- auto
- number

<br>

## Background

- background-attachment
  - scroll
  - fixed
- background-color
- background-image
  - none
  - url(-)
- background-position
  - direction1 direction2
- background-repeat
  - repeat
  - repeat-x
  - repeat-y
  - no-repeat
- background-size
  - auto
  - cover
  - contain

<br>

## Transition

- transition
  - property
  - duration
  - timing-function
    - ease
    - ease-in
    - ease-out
    - ease-in-out
  - delay

<br>

## Transform

### 2D 변환 함수

- translate(x, y)
- translateX(x)
- translateY(y)
- scale(x, y)
- rotate(deg)
- skewX(deg)
- skewY(deg)

### 3D 변환 함수

- rotateX(deg)
- rtateY(deg)
- perspective(distance)
  - 관찰 대상에 원근 거리 적용

### 3D 요소의 뒷면 숨김 여부

#### property

- backface-visibility

### value

- visible
- hidden

<br>

## Perspective

- 관찰 대상의 부모에 원근거리 추가

<br>

## Outline

- 공간을 차지하지 않는 외곽선

<br>

## Text Style

### 폰트

- font-family
- font-size
- font-weight
- font-style
- text-transform
  - none
  - capitalize
  - lowercase
  - uppercase
- text-decoration
  - none
  - underline
  - overline
  - line-through
- text-shadow

### 텍스트 레이아웃

- text-align
- text-indent
- writing-mode
- letter-spacing
- word-spacing
- line-height
- white-space
  - nowrap
    - 연속 공백 & 줄바꿈을 하나의 공백으로 표시
    - 긴 줄 줄바꿈 표시
  - pre-wrap
    - 연속 공백 그대로 표시
    - 긴 줄 그대로 표시
  - pre-line
    - 연속 공백 그대로 표시
    - 긴 줄 줄바꿈 표시
      <br>
- text-overflow
  - clip
    - 자르기
  - ellipsis
    - 자르고 잘린 부분을 ...으로 표시
- word-break
  - break-all
  - keep-all
- line-break
- overflow-wrap

<br>

## Box Model

### 구성

- content
- padding
- border
- margin

### 기타 프로퍼티

- border-radius
- box-sizing
  - content-box (default)
  - border-box

### 특징

- Margin Collapsing

  - 수직 인접한 두 요소가 존재할 경우에 작은 마진이 더 큰 마진으로 병합되어서 작은 마진이 적용이 안 된 것처럼 보이는 현상

<br>

## Placement

### Float

#### value

- none
- left
- right
- clear

#### 특징

- display 프로퍼티와 같이 사용 불가
- position: absolute와 같이 사용 불가

### Position

- static
- relative
- absolute
  - displa:block으로 자동 설정
  - 가로 너비를 최소로 설정
- fixed
  - display: block으로 자동 설정
  - 가로 너비를 최소로 설정
- sticky
  - top, right, bottom, left 프로퍼티 설정 필요
  - 부모 요소에 height 프로퍼티 설정 필요
  - 부모 요소에 overflow가 있을 경우 사용 불가

### Centering

#### 가로 중앙 정렬

- right: 0;
- left: 0;
- width: n;
- margin: 0 auto;

#### 가로 세로 중앙 정렬

- position: absolute;
- top: 0;
- right: 0;
- bottom: 0;
- left: 0;
- width: n;
- height: n;
- margin: auto;

#### 가로 세로 중앙 정렬

- display: flex;
- justify-content: center;
- align-items: center;

#### Image List

- position: absolute;
- top: n;
- left: 50%;
- width : calc(imageWidth \* count + padding\*2);
- height: n;
- margin-left: calc(-1 \* width / 2);

#### N:M Rate Video

- .container {  
   position: absolute;  
   top: 50%;  
   left: 50%;  
   width: N;  
   margin-top: calc(-1 \* width \* M / N / 2);  
   margin-left: calc(-1 \* width / 2);  
  }

- .container::before {  
   content: "";  
   display: block;  
   width: 100%;  
   height: 0;  
   padding-top: rate%;  
  }

<br>

## Display

- inline
- inline-block
- block
- none
- flex
- inline-flex
- grid
- inline-grid

<br>

## Layout

### Grid

#### 정의

- 2차원 레이아웃 모델

#### 구성

- Container
- Item

#### 사전 설정

- 컨테이너에 display: grid; 선언 설정

#### Grid Cell

- 그리드의 최소 단위

#### Grid Track

- 그리드 셀의 공간

#### 높이 n의 명시적 행 m개 추가 설정

- 컨테이너에 grid-template-rows: repeat(m, n); 설정

#### 폭 n의 명시적 열 m개 추가 설정

- 컨테이너에 grid-template-columns: repeat(m, n); 설정

#### 높이 n의 잠재적 행 m개 추가 설정

- 컨테이너에 grid-auto-rows: repeat(m, n); 설정

#### 폭 n의 잠재적 열 m개 추가 설정

- 컨테이너에 grid-auto-columns: repeat(m, n); 설정

#### 경계 여백 설정

- 컨테이너에 grid-gap: n 설정

#### 그리드 라인을 이용한 위치 설정

- 아이템에 grid-column-start, grid-column-end, grid-row-start, grid-row-end 프로퍼티 설정

### Flex Box

#### 정의

- 1차원 레이아웃 모델

#### 구성

- Container
- Item

#### 사전 설정

- 컨테이너에 display: flex; 선언 설정

#### 주축 설정

- 컨테이너에 flex-direction 프로퍼티 설정
  - row
  - row-reverse
  - column
  - column-reverse

#### 복수 행 설정

- 컨테이너에 flex-wrap 프로퍼티 설정
  - nowrap
  - wrap
  - wrap-reverse

#### 주축과 복수 행 설정

- 컨테이너에 flex-flow 프로퍼티 설정

#### 아이템 크기 설정

- 아이템에 flex-basis 프로퍼티 설정

#### 아이템 크기 증가 비율 설정

- 아이템에 flex-grow 프로퍼티 설정

#### 아이템 크기 감소 비율 설정

- 아이템에 flex-shrink 프로퍼티 설정

#### 아이템 크기와 증가, 감소 비율 설정

- 아이템에 flex 프로퍼티 설정

#### 메인 축 중심의 아이템 정렬 설정

- 컨테이너에 justify-content 프로퍼티 설정
  - flex-start
  - flex-end
  - center
  - space-between
  - space-around

#### 교차 축 중심의 아이템 정렬 설정

- 컨테이너에 align-items 프로퍼티 설정
  - flex-wrap: nowrap 설정 필요
  - stretch (default)
  - flex-start
  - flex-end
  - center
  - baseline

#### 교차 축 중심의 라인 정렬 설정

- 컨테이너에 align-content 프로퍼티 설정
  - flex-wrap: nowrap이 아닌 설정 필요
  - stretch (default)
  - flex-start
  - flex-end
  - center
  - space-between
  - space-around

#### 교차 축 중심의 개별 아이템 정렬 설정

- 아이템에 align-self 프로퍼티 설정
  - auto (default)
  - stretch
  - flex-start
  - flex-end
  - center
  - baseline

<br>
