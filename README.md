##### 🍑  Front_End 과정 1단계 

웹에서 사용되는 단위는 크게 절대적 단위와 상대적 단위로 크게 나눌 수 있다.  
절대적 단위랑 그 크기가 지정된 뒤에는 다른 요소에 의해 변경되지 않는다는 것이고    
상대적 단위는 크기자 지정된 뒤에도 다른 요소에 의해 변경될 수 있다는 것이다. 

💚 절대적단위 : px(픽셀) , cm (센치미터), mm (밀리미터), in (인치), pt (포인트) , pc (picas)  

 | Unit	|Description|  
 |---|---|
|cm	|centimeters|
|mm	|millimeters|
|in	|inches (1in = 96px = 2.54cm)|
|px *	|pixels (1px = 1/96th of 1in)|
|pt|	points (1pt = 1/72 of 1in)|
|pc	|picas (1pc = 12 pt)|

    
💙 상대적단위 : 퍼센트, em, rem과 뷰포트를 뜻하는 **v** 가 들어간 것들이다.   

> (body 폰트 사이즈 기본값을 16픽셀로 했을때 )16px == 1em == 100%,  14px == 0.8750em == 87,50% 

## px vs percent
```html
<style>
    .box { margin: 10px; background-color: orange;}
    .px { width: 50px;}
    .percent { width: 50%;}
    .parent { width: 150px;}
</style>
<h1>웹에서 사용되는 단위들</h1>
    <h2>부모가 없고 있고</h2>
    <div class="box px" >px</div>
    <div class="box percent">%</div>
    <div class="parent">
        <div class="box px" >parent px</div>
        <div class="box percent">parent % </div>
 </div>
```

## viewport를 단위로 사용하는 것들   
뷰포트를 사용하는 대표적인 단위는 vw, vh, vmin, vmax.  

- vw: 너비를 나타내며 뷰포트 너비의 백분율을 나타냅니다.  vw 앞에 있는 숫자는 뷰포트 너비의 백분율입니다. 10vw는 뷰포트 너비의 10%길이에 해당합니다. 

- vh (Viewport Height) : vw와 비슷한 개념으로 너비대신에 높이로 대치하는 것외에는 동일합니다. 그래서 100vw, 100vh라고 하면 화면전체크기를 채우는 것을 말합니다. 

- vmin, vmax : 단어에서 알 수 있듯이 min는 최소의 것을 선택, max는 최대의 것을 선택한다는 의미이다.    
   **viewport의 높이와 너비중 더 큰쪽(또는 작은)의 것을 선택하여 1vmax(vmin) = 높이/너비 중 더 큰쪽(작은)의 것(w의 1%와 같다.**
  
- vi : Viewport Inline의 약자로 문서의 인라인 방향을 나타냅니다. <br>
    가로 쓰기 방향에서 이것은 뷰포트의 너비에 해당하는 반면 <br>
    세로 쓰기 방향에서는 뷰포트의 높이를 나타냅니다. <br>
    이것은 **writing-mode** 에 대해 먼저 알아야 합니다 



## vw & vh   
```html
<style>
.box { margin: 10px; background-color: green;}
.parent { width: 300px;  height: 300px;  border: 2px solid;}
.percent { width: 50%;}
.vw { width: 10vw;}
.vh { height: 10vh;}
</style>
 <h2>vw &amp; vh</h2>
 <!--  너비의 크기를 뷰포트의 크기로 부터 계산하므로 유동적이다 -->
<div class="box percent"> % </div>
<div class="box vw">vw</div>
<div class="box vh">vh</div>

<div class="parent">
    <div class="box percent">parent % </div>
    <div class="box vw">parent vw</div>
    <div class="box vh">parent vh</div>
</div>

```   
1. 우선, 브라우저를 움직여서 브라우저의 너비와 높이가 변할때마다 vw와 vh의 크기가 달라지는 것을 확인한다.   
2. 그리고 퍼센트로 지정된 2개의 요소는 중 부모를 가진 요소는 브라우저의 크기에 상관없이 부모크기에 따라 자신의 크기가 지정된다는 것을 확인한다.
3. vw, vh 단위를 가진 요소는 부모의 유무에 상관없이 브라우저의 크기에 따라 자신의 크기가 결정된다는 것을 확인한다.

## vmax & vmin   
이것은 좀 헷갈리기 쉽다.  vmax는 더 큰것을 선택, vmin은 더 작은것을 선택하는 것해서 크기를 계산해서 적용한다는 것으로 아래와 같이 해보자.   

```html
<style>
* { padding: 0; margin: 0;}
 .box { width: 100px; height: 100px; background-color: red;}
 .box_vmax { width: 100vmax; height: 100px; background-color: green}
</style>

 <div class="box"></div>
 <div class="box_vmax"></div>

```   
브라우저의 높이가 더 큰 경우로, 브라우저의 개발자도구를 열고 아래 이미지의 테두리부분을 확인해 본다.  

<img width="700" alt="스크린샷 2023-12-25 오후 2 50 37" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/79ee7383-7c63-4db1-b10c-e1aa95f07a9d">


위 코드 중 ``` width:100vmax``` 에서 만약 vmax 대신 px 이었다면 100px로 브라우저의 크기에 상관없이 그대로 100px이다.   
그런데 vmax 이니까 브라우저의 너비와 높이 중 더 큰쪽인 height가 기준이 되고 
100 이니까 브라우저의 높이의 100퍼센트인 707를 width값으로 잡는 것이다.    
위의 이미지에서 브라우저의 height가 .box_vmax의 width 가 된것을 확인해보자.   


아래 이미지는 브라우저의 너비를 더 크게 했을 경우로써 .box_vmax의 width가 얼마로 계산되는지 확인해보자   

<img width="700" alt="스크린샷 2023-12-25 오후 3 05 34" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/e6ced778-39c0-4d45-ac2d-19245c7afdc7">



