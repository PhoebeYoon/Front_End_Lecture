##### 🍑  Front_End 과정 1단계 


**rel 속성은 현재 문서와 연결된 문서 사이의 관계를 지정합니다.**    


rel : relation 약자,    
href : hyper reference 의 약자   

- The path to the resource in the **href** attribute.   
- The type of resource in the **as** attribute.   

| 속성값  | 설명 |
|---|---|
|alternate | 프린트 페이지나 번역된 페이지와 같이 해당 문서의 대체 버전에 대한 링크를 제공함.|
|license| 해당 문서의 저작권 정보에 대한 링크를 제공함. |
|preconnect | 브라우저가 대상 리소스의 원본에 미리 연결하도록 명시함. |
|prefetch  | 사용자가 요청할 가능성이 있으므로, 브라우저가 대상 리소스를 미리 가져와 캐시(cache)하도록 명시함. |
| preload |  브라우저가 as 속성과 해당 대상과 관련된 우선순위에 따라 현재 탐색에 사용할 대상 리소스를 미리 가져와 캐시하도록 명시함. |
|stylesheet  | 	스타일 시트(stylesheet)로 사용할 외부 리소스를 불러옴. |
| search |  현재 문서 및 관련 페이지를 검색하는데 사용할 수 있는 리소스에 대한 링크를 제공함. |

```css
<link rel="stylesheet" type="text/css" href="/examples/media/expand_style.css">


```
## javascript 로딩시 asyn, defer 사용 설명 

<img width="874" alt="스크린샷 2023-12-27 오후 3 43 50" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/e6058b22-7a50-4602-b13f-bec5d45707ef">


```html
<link rel="stylesheet" href="style.css">
<link rel="preload" href="script.js" as="script">
<script  asyn src="script1.js" ></script>
</head>
<body>
    <div>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto, neque!
    </div>
    
</body>
```
[style.css]
```css
div { background-color:orange}
```

[script.js]
```js
document.querySelector('div').style.color="yellow"

```





