##### 🍑  Front_End 과정 1단계 

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
