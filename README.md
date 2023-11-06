##### 🍑  Front_End 과정 1단계 


## Image Lazy Loading이란 무엇인가
Image Lazy Loading은 페이지 안에 있는 실제 이미지들이 실제로 화면에 보여질 필요가 있을 때 로딩을 할 수 있도록 하는 테크닉입니다.  

웹 페이지 내에서 바로 로딩을 하지 않고 로딩 시점을 뒤로 미루는 것이라 볼 수 있습니다. 이 방식은 웹 성능과 디바이스 내 리소스 활용도 증가, 그리고 연관된 비용을 줄이는데 도움을 줄 수 있습니다. 

페이지를 로드하자마자 리소스를 로딩하는 일반적인 방식 대신, 실제로 사용자 화면에 보여질 필요가 있을 때까지 이러한 로딩을 지연하는 것입니다.

우리가 스크롤를 이용하여 하단에 위치한 이미지를 볼때를 생각해보면,
사용자가 1-2개의 이미지만 보고 해당 페이지를 빠르게 떠날수도 있습니다. 그러나 기본의 방식대로라면 이미지들은 모두 다운로드할때까지 계속됩니다.
사용자가 페이지에서 스크롤을 아래로 내림으로써, 이미지의 placeholder는 뷰포트(웹 페이지 내 보여지는 부분)에 다가오게 됩니다. 뷰포트에 보여지게되면 이미지를 로딩하도록 트리거를 일으킵니다.



laze loading을 다루는 방식은 페이지 내의 거의 모든 리소스에 적용할 수 있습니다. 예를 들어, SPA(Single Page Application) 내에서 JS 파일이 나중에까지 필요하지 않으면 초기에 로드해서 가져오지 않는 것이 가장 좋습니다. 이 처럼 이미지도 바로 보여질 필요가 없다가, 실제로 보여질 필요가 있을 때 로딩을 하는 것입니다

## DOMContentLoaded vs onload 차이
웹 문서를 만들때, '문서가 로드되는 시점'에 발생하는 이벤트로 주로 DOMContentLoaded와 onload를 사용합니다. 
DOMContentLoaded는 DOM 트리가 완성되는 즉시이고,   
onload는 문서의 모든 컨텐츠 ( css, script, images등)이 로드되었을때 이다.


## Lazy Loading을 다루는 여러가지 기술  
웹 페이지 내 이미지는 두 가지 방법으로 로드할 수 있습니다. 바로 <img>태그와 CSS 속성 중'background'를 이용하는 것입니다. 
### 1. img 태그

첫 번째는, 이미지 로딩을 사전에 막는 것입니다. 일반적으로 <img>태그를 이용해서 이미지를 로드하기 위해서, 브라우저는 태그 내 src 속성을 이용합니다. HTML 내 첫 번째 이미지든 1000번째 이미지이든, 혹은 뷰포트 밖에 있든 상관없이, 만약 브라우저가 src 속성을 가지면, 이미지를 무조건 로드합니다.

그래서 img태그의 src속성을 비워두고 data-src="이미지경로"로 이용하는 것입니다. 
이렇게한후에 해당 이미지가 뷰포트안에 들어오자마자 로딩할 수 있도록 하는 것입니다. 
이때 자바스크립트의 이벤트를 이용합니다. scroll, resize, orientationChange 이벤트리스너를 이용하면 됩니다. 
이미지의 위치를 이용하여 어떤 이미지가 뷰포트안에 들어왔는지 확인하고 data-src의 속성에 지정된 url를 img태그의 src 속성으로 전달하여 이미지를 로드합니다. 그후에 나중에 트리거 이벤트를 일으키기 위해 로딩을 지연시킬 이미지로 식별하던  lazy클래스를 제거합니다

```html
<style>
img {
  background: #F1F1FA;
  width: 400px;
  height: 300px;
  display: block;
  margin: 10px auto;
  border: 0;
}
</style>
<body>
<img src="https://ik.imagekit.io/demo/img/image1.jpeg?tr=w-400,h-300" />
<img src="https://ik.imagekit.io/demo/img/image2.jpeg?tr=w-400,h-300" />
<img src="https://ik.imagekit.io/demo/img/image3.jpg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image4.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image5.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image6.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image7.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image8.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image9.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image10.jpeg?tr=w-400,h-300" />
<script>
document.addEventListener("DOMContentLoaded", function() {
  var lazyloadImages = document.querySelectorAll("img.lazy");    
  var lazyloadThrottleTimeout;
  
  function lazyload () {
    if(lazyloadThrottleTimeout) {
      clearTimeout(lazyloadThrottleTimeout);
    }    
    
    lazyloadThrottleTimeout = setTimeout(function() {  // 🧠setTimeout()에 할당된 변수에는 실행의 결과로 number가 할당된다
        var scrollTop = window.pageYOffset;
        lazyloadImages.forEach(function(img) {
            if(img.offsetTop < (window.innerHeight + scrollTop)) {
              img.src = img.dataset.src;
              img.classList.remove('lazy');
            }
        });
        if(lazyloadImages.length == 0) { 
          document.removeEventListener("scroll", lazyload);
          window.removeEventListener("resize", lazyload);
          window.removeEventListener("orientationChange", lazyload);
        }
    }, 20);
  }
  
  document.addEventListener("scroll", lazyload);
  window.addEventListener("resize", lazyload);
  window.addEventListener("orientationChange", lazyload);
});
</script>
</body>
```
#### Intersection Observer API를 이용하여 lazy load를 구현한 예시:
우리는 이미지 로드를 지연시키기 위해 모든 이미지에 옵저버를 부착시킵니다.  엘리먼트가 뷰포트에 들어간 것은 API가 감지했을 때, isIntersecting 속성을 이용해서 URL을 data-src 속성에서 src 속성으로 이동시켜서 브라우저가 이미지를 로드하도록 트리거를 일으킵니다. 전부 로드되면 lazy 클래스명을 이미지에서 삭제하고 부착했던 옵저버를 제거합니다.

```html
<style>
    img {
  background: #F1F1FA;
  width: 400px;
  height: 300px;
  display: block;
  margin: 10px auto;
  border: 0;
}
  </style>
</head>
<body>
  
</body><img src="https://ik.imagekit.io/demo/img/image1.jpeg?tr=w-400,h-300" />
<img src="https://ik.imagekit.io/demo/img/image2.jpeg?tr=w-400,h-300" />
<img src="https://ik.imagekit.io/demo/img/image3.jpg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image4.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image5.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image6.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image7.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image8.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image9.jpeg?tr=w-400,h-300" />
<img class="lazy" data-src="https://ik.imagekit.io/demo/img/image10.jpeg?tr=w-400,h-300" />
<script>
  document.addEventListener("DOMContentLoaded", function() {
  var lazyloadImages;    

  if ("IntersectionObserver" in window) {
    lazyloadImages = document.querySelectorAll(".lazy");
    var imageObserver = new IntersectionObserver(function(entries, observer) {
      entries.forEach(function(entry) {
        if (entry.isIntersecting) {
          var image = entry.target;
          image.src = image.dataset.src;
          image.classList.remove("lazy");
          imageObserver.unobserve(image);
        }
      });
    });

    lazyloadImages.forEach(function(image) {
      imageObserver.observe(image);
    });
  } else {  
    var lazyloadThrottleTimeout;
    lazyloadImages = document.querySelectorAll(".lazy");
    
    function lazyload () {
      if(lazyloadThrottleTimeout) {
        clearTimeout(lazyloadThrottleTimeout);
      }    

      lazyloadThrottleTimeout = setTimeout(function() {
        var scrollTop = window.pageYOffset;
        lazyloadImages.forEach(function(img) {
            if(img.offsetTop < (window.innerHeight + scrollTop)) {
              img.src = img.dataset.src;
              img.classList.remove('lazy');
            }
        });
        if(lazyloadImages.length == 0) { 
          document.removeEventListener("scroll", lazyload);
          window.removeEventListener("resize", lazyload);
          window.removeEventListener("orientationChange", lazyload);
        }
      }, 20);
    }

    document.addEventListener("scroll", lazyload);
    window.addEventListener("resize", lazyload);
    window.addEventListener("orientationChange", lazyload);
  }
})
</script>

```

이벤트 리스너와 Intersection Observer 이 두 방법에 대해 이미지 로딩 시간을 비교해보면, 후자가 이미지를 로드하는 트리거가 훨씬 빠르며 스크롤할 때 이미지가 느리게 나타나지 않는 것을 확인할 수 있습니다.  
그러나 Intersection Observer API는 아직 모든 브라우저가 지원되고 있지 않습니다. 그렇기에 해당 API가 지원되지 않는 브라우저에서는 event listener 방식으로 사용하도록 해야 합니다.

그리고 **로딩 지연된 이미지들이 다운로드될 때 다른 감싸고 있는 콘텐트 내용들이 밀려나는 것을 방지하려면, 반드시 height와 width 속성을 <img>태그에 추가하거나 inline style로 직접 값을 지정해야 합니다.**

#### Native Lazy Loading 방식
아주 최신의 Google Chrome 브라우저 버전(Chroem 76)에서는 native lazy loading을 지원합니다. 해당 방식이 지원되면서, 개발자는 lazy loading을 구현하기 위해 임베딩 할 이미지에 'loading' 속성만 추가해주면 됩니다
```
<img src="example.jpg" loading="lazy" alt="..." />
<iframe src="example.html" loading="lazy"></iframe>
```
loading="lazy"의 속성에는 ,
- lazy - 뷰포트에서 일정한 거리에 닿을 때까지 로딩을 지연시킵니다.
- eager - 현재 페이지 위치가 위, 아래 어디에 위치하던 상관없이, 페이지가 로딩되자마자 해당 요소를 로딩합니다. 
- auto - 이 속성은 디폴트로 로딩을 지연하는 것을 트리거합니다. 기본적으로 이것은 loading 속성을 쓰지 않을 것과 같습니다.

### 2. CSS 속성 중 Background Image를 Lazy Loading 하는 방법
```html
  <style>
    * {font-family: sans-serif;}
#container {font-size: 20px; line-height: 30px;
  max-width: 600px;}
#bg-image.lazy {background-image: none;
   background-color: #F1F1FA;}
#bg-image {
  background-image: url("https://ik.imagekit.io/demo/img/image10.jpeg?tr=w-600,h-400");
  max-width: 600px;
  height: 400px;
}
  </style>

<script>
js코드는 위에 있는것과 동일합니다.
</script>
```


위 예시에서 주목할 점은 lazy loading 관련해서 구현한 자바스크립트 코드가 똑같다는 것입니다. 이벤트 리스너와 Intersection Observer API를 함께 이용해서 구현되어 있습니다. 트릭은 CSS 부분에 있습니다.

:peach: 올바른 image placeholder 사용법


placeholder는 실제 이미지가 로딩될 때까지 해당 이미지 자리에 대신 표시할 요소를 말합니다. 보통 개발자들은 이미지의 단색 이미지를 사용하거나 모든 이미지에다가 대체할 특정 이미지를 넣는 방식으로 구현합니다.
이전 예시 코드로 동작하던 lazy code를 본다면, placeholder로 밝은 회색을 사용하고 있습니다 특정 색상을 placeholder로 사용하는 대신, 사용하려는 실제 이미지의 주요한 색상을 이용하는 방법이 있습니다.

이미지의 첫 1x1 픽셀로 스케일을 감소 시키고 해당 픽셀 요소로 placeholder을 채우는 아주 간단한 방식입니다. 
ImageKit을 사용하면, 체인변환을 이용해서 주요 단일 색상을 얻을 수 있습니다. 

```
<!-- Original image at 400x300 -->
<img src="https://ik.imagekit.io/demo/img/image4.jpeg?tr=w-400,h-300" alt="original image" />

<!-- Dominant colour image with same dimensions -->
<img src="https://ik.imagekit.io/demo/img/image4.jpeg?tr=w-1,h-1:w-400,h-300" alt="dominant color placeholder" />

```

:peach: 모든 이미지에 lazy load를 적용하지 않는 것이 좋습니다.

참조) https://helloinyong.tistory.com/297

setTimeout() 에 대한 참조 : https://stackoverflow.com/questions/69523504/when-i-assign-to-a-variable-the-result-of-settimeout-how-does-the-function-insi


