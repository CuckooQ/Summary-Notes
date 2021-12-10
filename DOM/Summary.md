# DOM

## DOM

- HTML, XML문서의 프로그래밍 인터페이스.

## Data Type

- EventTarget
- Node
- Document
- Element
- Attr
- Window
- GlobalThis

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

### Window

- window.scrollTo(x,y)
- window.scollX  
  window.scrollY
