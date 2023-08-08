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
  div { border: 2px solid black; padding: 25px;  margin: 50px;}
  #example1 {
  background: url(./images/bee.jpg);
  background-repeat: no-repeat;
  background-size: 100% 100%;}
  #example2 {
  background: url(./images/bee.jpg);
  background-repeat: no-repeat;
  background-size: 75% 50%}
  #example3 {
  background: url(./images/bee.jpg);
  background-repeat: no-repeat;
  background-size: cover;}
  #example4 {
  background: url(./images/bee.jpg);
  background-repeat: no-repeat;
  background-size: contain;}
  
  img { width: 100px; height: 200px;}
  .c1 { object-fit: cover; }
  .c2 { object-fit: contain;}
  .c3 { object-fit: fill;} 
  /* fill는 object-fit의 기본값이어서 첫번째 이미지와 같은 결과이다 */
  /* contain은  가로세로의 비율을 유지하면서 이미지가 모두 보이도록 한다*/
  /* cover는 주어진 비율을 맞추면서 이미지를 삽입하되 남는 부분은 영역에서 제외한다  */
  .c4 {object-fit: cover;  width: 100px; height: 100px;}
  .c5 {object-fit: cover;  width: 100px; height: 100px;
      object-position: 50% 50%; }
 .c6 {object-fit: cover;  width: 100px; height: 100px;
      object-position: 80% 100%; }
    /* 위의 것과 비교할때  object-position: 50% 50%;  인것은 가운데 이미지가
    맞춰져 있는데 여기서 x축을 80%으로 하면 중심이 80% 이니까 
    이미지는 왼쪽으로 이동하고 Y축은 100%으로 하단끝에 맞춰지니까 이미지는 위쪽으로 조금 이동한다*/
    </style>
</head>
<body>
  <div id="example1">
        <h2>Hello World</h2>
        <p> 100% width and 100% height.</p>
      </div>

    <div id="example2">
        <h2>Hello World</h2>
        <p>75% width and 50% height.</p>
      </div>
      <div id="example3">
        <h2>Hello World</h2>
        <p>cover</p>
      </div>
      <div id="example4">
        <h2>Hello World</h2>
        <p>containe.</p>
      </div>
     <img   src="./images/93098.png" alt="">
     <h3>object-fit: cover;</h3>
     <img  class="c1" src="./images/93098.png" alt="">
     <h3>object-fit: contain;</h3>
     <img  class="c2" src="./images/93098.png" alt="">
     <h3>object-fit: fill;</h3>
     <img  class="c3" src="./images/93098.png" alt="">
     <h3>object-fit: cover; 속성과 object-position </h3>
     <img  class="c4" src="./images/print-01.jpg" alt=""> <br>
     <img  class="c5" src="./images/print-01.jpg" alt="">
     <img  class="c6" src="./images/print-01.jpg" alt="">
</body>
</html>
```

