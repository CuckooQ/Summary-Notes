# DOM

<br>

## 목차

#### [1. DOM](#DOM)

#### [2. Data Type](#Data-Type)

#### [3. Method](#Method)

- [Node](#Node)
- [Parent Node](#Parent-Node)
- [Document](#Document)
- [Element](#Element)
- [Window](#Window)

<br>

## DOM

- HTML, XML문서의 프로그래밍 인터페이스.

<br>

## Data Type

- EventTarget
- Node
- Document
- Element
- Attr
- Window
- GlobalThis

<br>

## Method

### Node

- node.textContent
- node.cloneNode(deep)

### Parent Node

- parentNode.appendChild(node)
- parentNode.removeChild(node)
- parentNode.replaceChild(newNode, oldNode)

### Document

- document.querySelector(selectors)
- document.querySelectorAll(selectors)
- document.getElementById(id)
- document.getElementByTagName(tagName)
- document.createElement(tagName, options)
- document.createDocumentFragment()
- document.documentElement
  - 문서의 루트 엘리먼트
  - 읽기 전용

### Element

- element.addEventListener(type, listener, options)
- element.removeEventListener(type, listener, options)
- element.setAttribute(name, vale)
- element.getAttribute(name)
- element.removeAttribute(name)
- element.innerHTML
- element.style.{attr}
- element.classList
  - add(className)
  - remove(className)
  - contains(className)
- element.scrollHeight - element.clientHeight
  - 요소에서 스크롤할 수 있는 최대 높이

### Window

- window.scrollTo(x,y)
- window.scollX  
  window.scrollY
