##### 🍑  Front_End 과정 1단계 

 예를 들어 화면 너비가 700px였다면 브라우저는 800px 너비 이미지 대신 1600px 너비 이미지를 여전히 다운로드했을 수 있습니다. 이는 브라우저가 화면의 픽셀 밀도도 고려하기 때문입니다. 고해상도 장치에 있거나 브라우저에서 줌 레벨이 높은 경우 브라우저는 실제로 화면의 여러 픽셀에 해당하므로 화면에 잘 보이도록 더 큰 이미지를 다운로드합니다. 장치 픽셀 밀도를 확인하려면 콘솔에서 window.devicePixelRatio를 사용할 수 있습니다.  



 
### 1. img 태그사용에 srcset 사용
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <img src="image-src.png" alt="" srcset="image-1x.png 1000w, image-2x.png 1280w, image-3x.png 1800w"  sizes="(max-width:1000px) 100vw , 800px">
    <hr>
    <img
  style="width: 100%; border-radius: 1rem;"
  src="https://placehold.co/3200x800/png"
  srcset="
    https://placehold.co/400x100/png   400w,
    https://placehold.co/800x200/png   800w,
    https://placehold.co/1200x300/png 1200w,
    https://placehold.co/1600x400/png 1600w,
    https://placehold.co/3200x800/png 3200w
  ">
</body>
</html>

```
위 코드의  두 번째 부분은 400w입니다. 이것은 w가 CSS 단위가 아니기 때문에 혼란스러울 수 있습니다.    
여기서 **w는 픽셀 단위의 이미지의 고유 너비를** 나타내며 이미지 파일의 실제너비입니다. 
그리고 
```
srcset="tree-400.jpg 400w, tree-800.jpg 800w, tree-1200.jpg 1200w"
// 위 코드의  srcset과 동일합니다. 
또한,

srcset="logo-100.jpg 1x, logo-150.jpg 1.5x, logo-200.jpg 2x"
위의 내용과 동일하지만 픽셀값대신 1.5x 및 2x와 같은 단위를 사용했습니다
이 단위는 화면의 픽셀 밀도를 나타냅니다.

예를 들어 누군가의 화면에 CSS 픽셀당 1.25개의 장치 픽셀 밀도가 있는 경우
픽셀을 늘리거나 흐리지 않고 사용할 수 있는 가장 작은 이미지이기 때문에
로고-150.jpg 이미지가 사용됩니다.
```


 sizes="(max-width: 800px) 100vw, 800px" 에서 화면의 너비가 800px보다 작은지 확인하는 것이고 
 두 번째 부분은 미디어 쿼리가 사실인 경우 이미지에 사용할 크기입니다. 이 경우 100vw를 사용하고 있는데, 이는 브라우저가 브라우저 창의 전체 너비를 기준으로 이미지 크기를 선택하기를 원한다는 것을 의미합니다.


```
화면에 브라우저의 사이즈와 ratio 출력
<script>
  window.addEventListener("resize", updateText);
  updateText()
function updateText(){
const data=document.querySelector("#data")
data.textContent=`width : ${window.innerWidth} , Ratio :${ window.devicePixelRatio }`
}
// 개발자도구에서 반응형보기 끄고 줌아웃해서 ratio:1 로 맞춘후 
// 화면사이즈 조절하고 리플레시 한다
</script>

```


srcset 다음에 size 라는 속성이 있습니다. 그러나 이 속성은 매우 강력하여 사용에 주의해야 합니다.  
그래서 여러개의 미디어 쿼리를 사용할 경우 미디어쿼리를 기술하는 순서가 중요합니다. 그래서 작은것부터 큰것 순으로 기술하는 것도 방법입니다.
또한 picture 태그를 사용하는 방법도 있습니다.

### 2. picture 태그사용에 srcset 사용
```html
<picture>
    <source media="(min-width:1280px)"  srcset="../images/image-4x.png">
    <source media="(min-width:1000px)"  srcset="../images/image-3x.png">
    <source media="(min-width:800px)"   srcset="../images/image-2x.png">
    <source media="(min-width:700px)"   srcset="../images/image-1x.png">
    <img src="../images/image-src.png" alt="src 써진그림">
</picture>

```


참조 ) https://blog.webdevsimplified.com/2023-05/responsive-images/
