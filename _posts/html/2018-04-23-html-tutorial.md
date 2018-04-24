---
layout: post
title: "html5 튜토리얼, html5 입문"
description: "w3schools를 보면서 공부한 튜토리얼 내용입니다."
tags: [html5, tutorial]
published: true
comments: true
image:
  feature: html5.png
---
---
### 1. What is HTML?
  - 웹 페이지 만들기 위한 표준 마크업 언어
  - **Hyper Text Markup Language** 줄임말
  - HTML elements은 tags로 나타냄

---

### 2. A Simple HTML Document

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```
`<!DOCTYPE html>`는 declaration, 나머지는 elements
- `<!DOCTYPE html>`: defines this document to be HTML5
- `<html>`: the root element of an HTML page
- `<head>`: contains meta information about the document
- `<title>`: specifies a title for the document
- `<body>`: contains the visible page content
- `<h1>`: defines a large heading
- `<p>`: defines a paragraph

---
### 3. HTML Tags
  - Element names surrounded by angle brackets
  - `<tag>content</tag>`

---
### 4. HTML Page Structure
<img src="/images/html/html-structure.png" alt="" />

---
### 5. HTML Documents
  - `<!DOCTYPE html>`: 모든 HTML5 문서의 시작(declaration)
  - `<html>` and `</html>`: HTML 문서의 시작과 끝
  - `<body>` and `</body>`: 보이는 부분은 모두 바디 태그 안에 넣기

---
### 6. HTML Links
```html
<a href="https://www.w3schools.com">This is a link</a>
```
  - `<a>`: HTML links 정의 태그
  - `href`: link의 목적지 주소 설정 속성

---
### 7. HTML Images
```html
<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142" />
```
  - `<img>`: HTML images 정의 태그
  - `src(source file)`, `alt(alternative text)`, `width`, `height`: 속성

---
### 8. HTML Buttons
```html
<button>Click me</button>
```
  - `<button>`: HTML buttons 정의 태그

---
### 9. HTML Lists
```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```
  - `<ul>`: unorderd/bullet list 태그
  - `<ol>`: ordered/numbered list 태그
  - `<li>`: list items 태그

---
### 10. HTML Elements
  - HTML element는 시작 태그부터 마지막 태그까지의 모든 것
  - `<html>` element는 whole document
  - `<body>` element는 document body
  - `<br>` or `<br />`: empty element
  - 필수는 아니지만 태그를 소문자로 쓰길 권장

---
### 11. HTML Attributes
  - 모든 HTML elements는 attributes를 가질 수 있다.
  - Attributes는 element에 대한 추가적인 정보를 제공한다.
  - 항상 시작 태그에 명시된다.
  - 주로 name="value"의 포맷 형식을 사용한다.
  - 필수는 아니지만 속성을 소문자로 쓰길 권장
  - 속성 value값에 ""가 필수 아니지만 쓰길 권장(생략, '' 가능)


---
### 12. HTML Headings, Paragraphs, Horizontal Rules, Line Break
  - `<h1>` to `<h6>`: most to least important headings
  - `<p>`: paragraph(문단) 정의
  - `<hr>`: a thematic break 정의(수평선 그어짐)
  - `<br>`: a line break(줄 바꿈, 엔터 기능)
  - `<pre>`: preformatted text, 태그 안에 작성한 대로 써짐

---
### 13. HTML Styles
  - The HTML Styles Attribute
    - syntax: `<tagname style="property:value;">`
    - property: CSS property, value: CSS value
  - HTML Background Color, Text Color, Fonts, Text Size, Text-Alignment
    ```html
    <body style="background-color:powderblue;">
    <h1 style="color:blue;">
    <p style="font-family">
    <h1 style="font-size:300%;">
    <h1 style="text-align:center;">
    ```

---
### 14. HTML Text Formatting
  - HTML Formatting Elements
    - `<b>` - Bold text
    - `<strong>` - Important text(bold + semantic importance)
    - `<i>` - Italic text
    - `<em>` - Emphasized text(i + semantic importance)
    - `<mark>` - Marked/highlighted text(형광펜 처리)
    - `<small>` - Small text
    - `<del>` - Deleted text(--- 처리)
    - `<ins>` - Inserted text(underline 처리)
    - `<sub>` - Subscript text(글씨 밑으로 내림)
    - `<sup>` - Superscript text(글씨 위로 올림)

---
### 15. HTML Quotation and Citation Elements
  - `<q>` - Short Quotations(짧은 인용, 작은 따옴표)
  - `<blockquote>` - Quotations(들여쓰기 + 문단 인용)
  - `<abbr>` - abbreviation or acronym (축약어 줄임말 등에 사용)
  - `<address>` - 문서나 기사의 연락처에 사용, 주로 Italic체 사용, 앞 뒤로 line break
  - `<cite>` - work의 title, italic체 사용 (미술 작품의 제목 등에 사용)
  - `<bdo>` - Bi-Directional Override, 글자 쓰는 방향 바꿀 때 사용

---
### 16. HTML Comments
  - syntax: `<!-- Write your comment here -->`

---
### 17. HTML Styles - CSS
  - Styling HTML with CSS
    - CSS stands for Cascading Style Sheets.
    - CSS can be added to HTML elements in 3 ways
      - Inline - by using the style attribute in HTML elements
      - Internal - by using a <style> element in the <head> section
      - External - by using an external CSS file
    - id속성은 #으로(bookmark시에도 사용), class속성은 .으로 구분

---
### 18. HTML Block and Inline Elements
  - Block Elements
    - new line으로 시작 + full width available
    - 대표적으로 div element(다른 엘리먼트 container, class, id, style과 주로 같이 사용)
    - `<address>` `<article>` `<aside>` `<blockquote>` `<canvas>` `<dd>` `<div>`
    - `<dl>` `<dt>` `<fieldset>` `<figcaption>` `<figure>` `<footer>` `<form>`
    - `<h1-h6>` `<header>` `<hr>` `<li>` `<main>` `<nav>` `<noscript>` `<ol>`
    - `<output>` `<p>` `<pre>` `<section>` `<table>` `<tfoot>` `<ul>` `<video>`
  - Inline Elements
    - new line으로 시작 X  + 필요한 만큼의 width
    - 대표적으로 span element(text container, class, id, style과 주로 같이 사용)
    - `<a>` `<abbr>` `<acronym>` `<b>` `<bdo>` `<big>` `<br>` `<button>` `<cite>`
    - `<code>` `<dfn>` `<em>` `<i>` `<img>` `<input>` `<kbd>` `<label>` `<map>`
    - `<object>` `<q>` `<samp>` `<script>` `<select>` `<small>` `<span>` `<strong>`
    - `<sub>` `<sup>` `<textarea>` `<time>` `<tt>` `<var>`

---
### 19. HTML Classes
  - One or more class names for an HTML element
  - Using the class Attribute in CSS
    - `<h2 class="city">`
    - style: `.city{ color: white; }`
  - Using the class Attribute in JavaScript
    - `<h2 class="city">`
    - script: `function{ var x = document.getElementByClassName("city"); }`

---
### 20. HTML Id
  - A unique id for an HTML element(HTML에서 id의 value 유일해야 함, 띄어쓰기 불가능)
  - Using the id Attribute in CSS
    - `<h1 id="myCity">`
    - style: `#myHeader{ color: black; }`
  - Using the id Attribute in JavaScript
    - `<h1 id="myCity">`
    - script: `function{ document.getElementById("myCity").innerHTML = "Hi"; }`
  - Bookmark with ID and Links
    - Create a bookmark: `<h2 id="C4">Chapter 4</h2>`
    - Add a link to the bookmark: `<a href="#C4">Jump to Chapter 4</a>`

---
### 21. HTML Iframes
  - An iframe: 웹 페이지 속에 웹페이지
  - syntax: `<iframe src="URL"></iframe>`

---
### 22. HTML JavaScript
  - JavaScript makes HTML pages more dynamic and interactive.
  - The HTML <script> Tag
    - client-side script (JavaScript)
    - contains scripting statements, or points to an external script file(src)
    - image manipulation, form validation, dynamic changes of content 등에 사용
    - HTML element 선택 위해 `document.getElementById()` 자주 사용
  - A Taste of JavaScript(자바스크립트 예시)
    - JavaScript can change HTML content
      - `document.getElementById("demo").innerHTML = "Hello JavaScript!";`
    - JavaScript can change HTML styles
      - `document.getElementById("demo").style.fontSize = "25px";`
      - `document.getElementById("demo").style.color = "red";`
      - `document.getElementById("demo").style.backgroundColor = "yellow";`
    - JavaScript can change HTML attributes
      - `document.getElementById("image").src = "picture.gif";`
  - The HTML <noscript> Tag
    - 브라우저에서 script 못 읽을 시에 대체 내용 제공

---
### 23. HTML File Paths
  - File Paths는 밑과 같은 외부파일 연결시에 사용
    - Web Pages
    - Images
    - Style sheets
    - JavaScript
  - Absolute File Paths
  - Relative File Paths

---
### 24. HTML Head
  - The HTML <head> Element
    - html과 body 태그 사이에 위치, metadata(data about data)의 container
    - metadata: data about the HTML document
    - 주로 document title, character set, styles, links, scripts 등을 정의
    - 주요 태그: `<title>` `<style>` `<meta>` `<link>` `<script>` `<base>`
  - The HTML <title> Element
    - title of the document 정의, 모든 html 문서에 필요
    - 브라우저 탭, 즐겨찾기, 검색엔진 결과 위해 필요
  - The HTML <style> Element
    - define style information for a single HTML page
  - The HTML <link> Element
    - used to link to external style sheets
  - The HTML <meta> Element
    - character set, page description, keywords, author 등을 명시
    - character set: `<meta charset="UTF-8">`
    - description of web page: `<meta name="description" content="Web tutorials">`
    - keywords for search engines: `<meta name="keywords" content="HTML, CSS">`
    - author of a page: `<meta name="author" content="John Doe">`
    - refresh document every 30s: `<meta http-equiv="refresh" content="30">`
  - Setting The Viewport
    - HTML5는 웹 디자이너가 `<meta>` 태그로 viewport 관리하게 해줌
    - viewport: user에게 웹 페이지가 보이는 부분, device(핸드폰 등)에 따라 달라짐
    - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
    - 모든 웹 페이지에 이 `<meta>` viewport element 넣어야 함
  - The HTML <script> Element
    - define client-side JavaScripts
  - The HTML <base> Element
    - base URL과 base target 지정(해당 웹페이지의 모든 relative URL에 대해)
    - `<base href="https://www.w3schools.com/images/" target="_blank">`
  - Omitting <html>, <head> and <body>?
    - HTML5 standard에서는 `<html>` `<body>` `<head>` tag 모두 생략 가능

---
### 25. HTML Layouts
  - HTML Layouts Elements
    - 웹사이트는 보통 컨텐츠를 다양한 컬럼안에서 보여줌(잡지나 신문 등)
    - HTML5는 new semantic element를 제공(웹페이지의 다른 파트 정의)
    <img src="/images/html/html-layout.gif" alt="" />  
    - `<header>` - Defines a header for a document or a section
    - `<nav>` - Defines a container for navigation links
    - `<section>` - Defines a section in a document
    - `<article>` - Defines an independent self-contained article
    - `<aside>` - Defines content aside from the content (like a sidebar)
    - `<footer>` - Defines a footer for a document or a section
    - `<details>` - Defines additional details
    - `<summary>` - Defines a heading for the <details> element
  - HTML Layout Techniques(multicolumm layout 만드는 4가지 방법)
    - HTML tables
      - `<table>` 태그는 layout tool을 위한게 아님. page layout으로 사용 비추천
    - CSS framework
      - layout 빠르게 만들기 위한 framework 사용 [W3.CSS](https://www.w3schools.com/w3css/default.asp) or [Bootstrap](https://www.w3schools.com/bootstrap/default.asp)
    - CSS float property
      - css float property 사용하여 웹 전체 레이아웃 만듦
      - 가장 흔한 사용법, 배우기 쉽지만 flexible하지 못함
    - CSS flexbox
      - 새로운 layout mode in CSS3
      - 다른 디바이스, 사이즈에 적용 가능, IE10과 이전 버전 작동 X

---
### 26. HTML Responsive Web Design
  - What is Responsive Web Design?
    - Using HTML and CSS to resize, hide, shrink, enlarge, or move the content
  - Setting The Viewport
    - 반응형 웹페이지를 위해서는 모든 웹 페이지에 아래의 코드 입력 해야함
    - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
  - Responsive Images
    - If the CSS width property is set to 100%, 반응형 이미지로 화면 내 가능한 사이즈만큼 커짐
    - If the max-width property is set to 100%, 원래 사이즈까지만 커짐
    - picture->source->media 조정시에 width에 따라 사진 바꾸기 가능
  - Responsive Text Size
    - viewport width로 text size 조정 가능
    - Viewport: browser window size, 1vw = 1% of viewport width.
    - `<h1 style="font-size:10vw">Hello World</h1>`
  - Media Queries
    - browser size마다 다른 style로 정의 가능

    ```html
    <style>
    .left, .right {
      float: left;
      width: 20%; /* The width is 20%, by default */
    }

    .main {
      float: left;
      width: 60%; /* The width is 60%, by default */
    }

    /* Use a media query to add a breakpoint at 800px: */
    @media screen and (max-width: 800px) {
      .left, .main, .right {
        width: 100%; /* Width is 100%, when the viewport is 800px or smaller */
      }
    }
    </style>
    ```
  - Responsive Web Design - Frameworks
    - free & easy to use
    - Using W3.CSS
    - Bootstrap

---
### 27. HTML Computer Code Elements (monospace font)
  - HTML <kbd> For Keyboard Input
    - `<kbd>`: user input 나타냄, keyboard input or voice commands
  - HTML <samp> For Program Output
    - `<samp>`: program 이나 computing system output 나타냄
  - HTML <code> For Computer Code
    - `<code>`: fragment of computer code 나타냄, 줄내림 안됨
    - `<pre><code>`: 로 쓰면 줄내림 가능
  - HTML <var> For Variables
    - `<var>`: variable 나타냄, 수학 표현, 변수 등
    - `Einstein wrote: <var>E</var> = <var>mc</var><sup>2</sup>.`

---
### 28. HTML Entities
  - Reserved characters in HTML character entities로 사용되야 함.
  - keyboard에 없는 character도 entities로 대체 가능.
  - Useful HTML Character Entities
  <img src="/images/html/html-character-entities.png" alt="" />

---
### 29. HTML Uniform Resource Locators
  - URL - Uniform Resource Locator - web address
  - composed of words(w3schools.com) 또는 IP address(192.68.20.50)로 표기
  - ex) `scheme://prefix.domain:port/path/filename`
  - scheme - defines the type of Internet service (most common is http or https)
  - prefix - defines a domain prefix (default for http is www)
  - domain - defines the Internet domain name (like w3schools.com)
  - port - defines the port number at the host (default for http is 80)
  - path - defines a path at the server (If omitted: the root directory of the site)
  - filename - defines the name of a document or resource

---
### 30. HTML and XHTML
  - What is XHTML?
    - HTML written as XML
    - stands for EXtensible HyperText Markup Language
    - almost identical to HTML
    - stricter than HTML
    - HTML defined as an XML application
    - supported by all major browsers
  - Why XHTML?
    - HTML이 문법 맞지 않게 쓰여질 때 많은데 그래도 돌아감
    - XML is a markup language where documents must be marked up correctly.
    - If you want to study XML, please read our [XML tutorial](https://www.w3schools.com/xml/default.asp).
    - By combining the strengths of HTML and XML, XHTML was developed.
    - XHTML is HTML redesigned as XML.
  - The Most Important Differences from HTML
    - Document Structure
      - XHTML DOCTYPE is mandatory
      - The xmlns attribute in <html> is mandatory
      - `<html>` `<head>` `<title>` `<body>` are mandatory
    - XHTML Elements
      - XHTML elements must be properly nested
      - XHTML elements must always be closed
      - XHTML elements must be in lowercase
      - XHTML documents must have one root element
    - XHTML Attributes
      - Attribute names must be in lower case
      - Attribute values must be quoted
      - Attribute minimization is forbidden

---
### 참조
  - [w3schools.com](https://www.w3schools.com/html/default.asp)
