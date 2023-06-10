
##### 🍑  Front_End 과정 1단계 


## view port에 대한 설명

```html   
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, 
   maximum-scale=1.0, minimum-scale=1.0, user-scalable=no, target-densitydpi=medium-dpi">
<!--    <link rel="apple-touch-icon" href="second.png">-->
<!--    <link rel="shortcut icon" href="02.jpg">-->
    <title>해상도별보기</title>
    <style>
       body{ margin: 0; padding: 0;}
      #dpi{ width: 320px; height: 480px;  border:4px dashed green; 
            background: url(800x1920.png);   margin: auto;  }
       @media  only screen  and (-webkit-min-device-pixel-ratio:1.5) {
             #dpi{ width: 320px; height: 480px; border:4px solid red; 
                 background: url(640x960.png); margin: auto; } 
             }
        @media only screen and (-webkit-min-device-pixel-ratio: 2) {
            #dpi{ width: 320px; height: 480px;  border:4px solid yellow;
                background: url(800x1280.png); margin: auto;  } 
        }
        @media only screen and (-webkit-min-device-pixel-ratio:3) {
            #dpi{ width: 320px; height: 480px; border:4px solid magenta;
                background: url(800x1920.png); margin: auto; }  
        }
        @media only screen and (-webkit-min-device-pixel-ratio: 4) {
            #dpi{ width: 320px; height: 480px; 
            border:4px solid blue; margin: auto;   } 
        }
    </style>
</head>
<body>
    <div id="dpi"></div>
</body>
</html>
```   


### 접속한 디바이스가 모바일일 경우

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>브라우저테스트</title>
</head>
<body>
  <script type="text/javascript">
    var mobileKeyWords = new Array('iPhone', 'iPod', 'BlackBerry', 'Android', 'Windows CE', 
    'LG', 'MOT', 'SAMSUNG', 'SonyEricsson', 'Windows Phone');
    for (var word in mobileKeyWords) {
      if (navigator.userAgent.match(mobileKeyWords[word]) != null) {
        location.href = "whatdevice.html";   <-- 여기에 모바일로 접속시 이동한 페이지를 적어줍니다 
        break;
      }
    }
  </script>
 접속한 디바이스를 맞춰보자
</body>
</html>
```

#### 미디어 쿼리를 자바스크립트로 실행할때 (max-width:600px)값을 matchMedia()를 사용한다
주요내용은,   
```js
let mql = window.matchMedia("(max-width: 600px)");
document.querySelector(".mq-value").innerText = mql.media;
```     

```html
  <style>
    body { background: deepskyblue;}
    @media (max-width:800px) {
      body { background-color: orange;}
    }
  </style>
  <title>Document</title>
</head>
<body>
  <span class="mq-value"></span>
  <span class="mq-match"></span>
<script>
let mql = window.matchMedia("(max-width:800px)");
document.querySelector(".mq-value").innerText = mql.media;
document.querySelector(".mq-match").innerText = mql.matches;
if (mql.matches) {
  document.querySelector(".mq-value").innerText  ="Done"
}
</script>

```
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
<p></p>
<script>
const para = document.querySelector("p"); // This is the UI element where to display the text
const mql = window.matchMedia("(max-width: 600px)");

mql.addEventListener("change", (event) => {
  if (event.matches) {
    // The viewport is 600 pixels wide or less
    para.textContent = "This is a narrow screen — less than 600px wide.";
    document.body.style.backgroundColor = "red";
  } else {
    // The viewport is more than 600 pixels wide
    para.textContent = "This is a wide screen — more than 600px wide.";
    document.body.style.backgroundColor = "blue";
  }
});
</script>
</body>
</html>
```




