# Front_End_Lecture

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


### 접속한 디바이스의 종류를 알아내는 코드

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




