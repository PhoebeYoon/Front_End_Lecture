##### 🍑  Front_End 과정 1단계 

## aspect-ratio

엘리먼트의 크기를 지정할때 보토은 width, height를 지정한다. 만약 div태그에 아무 내용도 없는 상태에서 width만 지정한다면 화면에 표시되지 않는다. 왜냐하면 height를 지정하기 않았기 때문이다. 여기에 aspect-ratio :3/1 로 지정하고 개발자도구에서 확인해보면 height가 크기를 갖고 브라우저에 표시된다. 
```html
<style>
    div { width: 90px; background-color: orange; 
    /* height: 50px; */
    aspect-ratio: 3 /1 ;}
</style>
<div class="box"></div>
```



