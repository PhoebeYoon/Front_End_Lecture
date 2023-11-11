##### 🍑  Front_End 과정 1단계 

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


