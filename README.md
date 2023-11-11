##### 🍑  Front_End 과정 1단계 


## min-height에 자세히 알아보자
mdn에 정의된 내용은 ,  
The min-height CSS property sets the minimum height of an element. It prevents the used value of the height property from becoming smaller than the value specified for min-height   
( min-height CSS 속성은 요소의 최소 높이를 설정합니다. 높이 속성의 사용 값이 min-height에 지정된 값보다 작아지는 것을 방지합니다 )

그런데 만약에 
```html
   <style>
.hero {  background-color: pink;  height: 75vh;  /* min-height: 75vh; */  }
h1 { height: 50%; border:1px solid;}
    </style>
 <div class="hero">
Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sit ipsa exercitationem veniam quisquam ex, culpa debitis at maiores, quia inventore recusandae hic asperiores quos perspiciatis dolorum! Minus cum voluptatem odit!
<h1>Heading</h1>
</div>
```
``` .hero ```가 height로 지정이 되면 h1도 50%의 크기를 제대로 설정된다.   
그런데 ```.hero 가 min-height로```  지정되면 h1는 height를 제대로 계산하지 못한다.  

그 이유는 min-height는 최대의 값을 가지는 것이고 브라우저의 크기에 따라 달라지기 때문에 h1이 height를 잡기가 어려운 것이다.   
그런 이유로 height 속성을 사용하여 크기를 고정시키면 
    h1는 해당 크기에서 50%를 계산할 수 있기 때문에 원하는대로 모양이 나오는 것이다. 

뭐 매우 간단한 얘기지만 min의 의미를 제대로 이해하지 못하면 헷갈릴 수 있다.   

