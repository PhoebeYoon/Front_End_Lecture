##### 🍑  Front_End 과정 1단계 
#### img  태그속성
- width
- height
- src
- alt
- srcset
- usemap
이외에 css 속성으로는
- object-fit
- object-position

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    img { border: 1px solid; width: 200px; height: 150px;}

/*  object-fit는 이미지를 중앙에 위치시키는 것을 원칙으로 한다 */
    img { object-fit: fill}
    img { object-fit: contain}
    img { object-fit: cover}
    img { object-fit: fill}

    /* object-fit는 원래 중앙, 50% 50% 가 기본값으로 중앙에서 배치되지만 
    이것을 변경하려면 object-position으로 이동해야 한다*/
    img { object-fit: cover}
    img { object-position: top left;}
    img { object-position: bottom right;}
    img { object-position: 15% 100%;}
  </style>
</head>
<body>
  <img src="../images/sim.png" alt=""> <br>
</body>
</html>
```

