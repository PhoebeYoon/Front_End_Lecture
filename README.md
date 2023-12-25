##### 🍑  Front_End 과정 1단계 

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
.vw { width: 50vw;}
.vh { width: 50vh;}
</style>
<h2>vw &amp; vh</h2>
 <!--  너비의 크기를 뷰포트의 크기로 부터 계산하므로 유동적이다 -->
<div class="box vw">vw</div>
<div class="box vh">vh</div>

```
브라우저의 너비와 높이가 변할때마다 vw와 vh의 크기가 달라진다.    










### viewport를 단위로 사용
기존의 뷰포트를 사용하는 단위는 vw, vh, vmin, vmax 이었으나 현재는 더 많이 늘어났습니다. 이런 내용을 여기에서 다루어볼 예정입니다   

- vw: 너비를 나타내며 뷰포트 너비의 백분율을 나타냅니다.  vw 앞에 있는 숫자는 뷰포트 너비의 백분율입니다. 10vw는 뷰포트 너비의 10%길이에 해당합니다. 

- vh (Viewport Height) : vw와 비슷한 개념으로 너비대신에 높이로 대치하는 것외에는 동일합니다. 그래서 100vw, 100vh라고 하면 화면전체크기를 채우는 것을 말합니다. 

- vmin, vmax : 단어에서 알 수 있듯이 min는 최소, max는 최대를 뜻합니다.   
- vi : Viewport Inline의 약자로 문서의 인라인 방향을 나타냅니다. <br>
    가로 쓰기 방향에서 이것은 뷰포트의 너비에 해당하는 반면 <br>
    세로 쓰기 방향에서는 뷰포트의 높이를 나타냅니다. <br>
    이것은 **writing-mode** 에 대해 먼저 알아야 합니다 
