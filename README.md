##### 🍑  Front_End 과정 1단계 

## preload
특정소소를 빠르게 로딩하기 위해 우선순위를 부여하는 방법으로 사용한다.
head 태그안에 지정한다.  

```html
<link rel="preload" as="script" href="critical.js">
<link rel="preload" as="style" href="example.css">
<link rel="preload" as="image" href="high-image.png">
<link rel="preload" href="ComicSans.woff2" as="font" type="font/woff2" crossorigin>

```   
- 여기서 as는 리소스의 유형을 알려주는 것으로 유형이 올바르지 않으면 브라우저는 해당 소스를 사용할 수 없다.   
- 또한 preload는 같은 소스를 중복해서 사용하지 않도록 해야한다. 
- 폰트를 preload 할때는 'crossorigin'를 추가합니다. crossorigin 속성없이 미리 로드된 글꼴은 두 번 가져오게 됩니다.   

>참고: preload는 모든 최신 브라우저에서 지원됩니다.


## preconnect 
현재 페이지에서 외부도메인에 있는 소스를 참조할때 해당 브라우저에게 미리 외부도메인을 연결하도록 설정할 수 있다.
preconnect가 그것인데 이렇게하면 브라우저는 필요한 소켓을 미리 설정할 수 있기 때문에 DNS, TCP, TLS 왕복에 필요한 시간을 절약할 수 있다.
```
<link rel="preconnect" href="http://example.com">

```


### 📖 이미지 로드시 낮은 ➡️ 높은용량으로 미리로드함으로써 더 나은 로딩만들기

```html
  <link rel="preload" as=image href="./img-lower.png" fetchpriority="high">

<style>
img { font-size: 1.5rem; font-style: italic; <-- 이미지를 제대로 로딩하지 못할때 alt속성에 입힐 글자효과
    max-width: 100%; 
    background-size: cover; height: auto;
    vertical-align: middle;
    background-image: url(./img-lower.png);
}
</style>
<img src="./img-high.png" alt="This is example how to access  every pages">
```
출처: https://csswizardry.com/2023/09/the-ultimate-lqip-lcp-technique/    
https://web.dev/articles/preload-critical-assets?hl=ko





