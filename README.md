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
