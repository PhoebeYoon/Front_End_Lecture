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



## viewport를 단위로 사용하는 것들   
뷰포트를 사용하는 대표적인 단위는 vw, vh, vmin, vmax.  

- vw: 너비를 나타내며 뷰포트 너비의 백분율을 나타냅니다.  vw 앞에 있는 숫자는 뷰포트 너비의 백분율입니다. 10vw는 뷰포트 너비의 10%길이에 해당합니다. 

- vh (Viewport Height) : vw와 비슷한 개념으로 너비대신에 높이로 대치하는 것외에는 동일합니다. 그래서 100vw, 100vh라고 하면 화면전체크기를 채우는 것을 말합니다. 

- vmin, vmax : 단어에서 알 수 있듯이 min는 최소, max는 최대를 뜻합니다.   
- vi : Viewport Inline의 약자로 문서의 인라인 방향을 나타냅니다. <br>
    가로 쓰기 방향에서 이것은 뷰포트의 너비에 해당하는 반면 <br>
    세로 쓰기 방향에서는 뷰포트의 높이를 나타냅니다. <br>
    이것은 **writing-mode** 에 대해 먼저 알아야 합니다 
