# HTML

<br>

## 목차

#### [1. Key Principle](#Key-Principle)

#### [2. Basic Tags](#Basic-Tags)

#### [3. Semantic Tags](#Semantic-Tags)

#### [4. Inline , Block Tag](#Inline-Block-Tag)

#### [5. HTML Entities](#HTML-Entities)

#### [6. Events](#Events)

<br>

## Key Principle

- Semantic HTML

<br>

## Basic Tags

- html
  - lang
- head
- body
- title
- meta
  - charset
  - name
    - author
    - description
    - viewport
    - twitter:card
    - twitter:site
    - twitter:title
    - twitter:description
    - twitter:image
    - twitter:url
  - content
  - property
    - og:type
    - og:site_name
    - og:title
    - og:description
    - og:image
    - og:url
- script
  - src
  - defer
  - async
- link
  - rel
    - stylesheet
    - icon
  - href
- style
- ol
- ul
- li
- iframe
- div
- span
- p
- strong
- h1 - h6
- i
- br
- hr
- img
  - src
  - alt
  - width
  - height
- a
  - href
  - target
  - title
  - referrerpolicy
  - download
- button
  - type
    - submit (default)
    - button
    - reset
  - name
  - value
  - autofocus
  - disabled
- input
  - type
    - text (default)
    - button
    - checkbox
    - color
    - date
    - datetime-local
    - email
    - file
    - hidden
    - image
    - password
    - radio
    - range
    - reset
    - search
    - submit
    - time
    - tel
    - url
    - week
  - name
  - value
  - autofocus
  - disabled
- form
  - name
  - action
  - method
    - get
    - post
  - accept-charset
  - enctype
  - novalidate
- fieldset
- legend
- label
- audio
  - 포맷
    - mp3
    - wav
    - ogg
  - autoplay
  - controls
  - loop
  - muted
  - playbackRate
  - preload
    - auto
    - metadata
    - none
  - src
- canvas
  - width
  - height
- datalist
- option
- details
  - open
- summary
- dialog
  - open
- figure
- figcaption
- mark
- meter
  - max
  - min
  - value
  - high
  - low
  - optimum
- progress
  - max
  - value
- time
  - datetime
- video
  - 포맷
    - mp4
    - webM
    - ogg
  - autoplay
  - controls
  - loop
  - muted
  - playbackRate
  - poster
  - preload
    - auto
    - metadata
    - none
  - src
  - width
  - height

<br>

## Semantic Tags

- header
- main
- footer
- hgroup
- nav
- section
- article
- aside
- address

<br>

## Inline, Block Tag

### Inline Tag

- 콘텐츠의 흐름을 끊지 않고, 태그에 할당된 공간만 차지하는 요소.

- 베이스 라인 아래에 특정 공간 차지.

- 크기 설정 불가.

- margin, padding, top, bottom 설정 불가.

- 크기 설정이 필요한 경우, display: inline-block으로 설정.

- 종류
  - a
  - audio
  - button
  - canvas
  - datalist
  - iframe
  - img
  - input
  - label
  - mark
  - meter
  - progress
  - span
  - strong
  - textarea
  - time
  - video
  - ::before
  - ::after

### Block Tag

- 부모 요소의 전체 공간을 차지하려 너비가 최대한 늘어나는 요소.

<br>

## HTML Entities

- `&nbsp;`
- `&lt;`
- `&gt;`
- `&amp;`
- `&quot;`
- `&apos;`
- `&copy;`
- `&reg;`

## Events

### Window

- onload
- onbeforeunload
- onunload
- onerror
- ononline
- onoffline
- onpageshow
- onpagehide
- onbeforeprint
- onafterprint
- onresize
- onmessage
- onpopstate
- onhashchange
- onstorage

### Form

- onsubmit
- oninput
- onchange
- onselect
- onfocus
- onblur
- oninvalid
- onreset
- onsearch
- oncontextmenu

### Keyboard

- onkeypress
- onkeydown
- onkeyup

### Mouse

- onclick
- ondbclick
- onmousedown
- onmouseup
- onmouseover
- onmousemove
- onmouseout
- onwheel

### Drag

- ondrag
- ondragstart
- ondragend
- ondrop
- ondragenter
- ondragover
- ondragleave
- onscroll

### Clipboard

- oncopy
- oncut
- onpaste

### Media

- onprogress
- onstalled
- onsuspend
- onloadstart
- onabort
- onloadedmetadata
- onloadeddata
- oncanplay
- oncanplaythrough
- onplay
- onplaying
- onpause
- onended
- ontimeupdate
- onvolumechange
- onratechange
- oncuechange
- ondurationchange
- onseeking
- onseeked
- onerror
- onwaiting
- onemptied

### Misc

- ontoggle
