##### 🍑  Front_End 과정 1단계 


## width : px, % , auto   
특별한 크기를 지정하기 않고 태그의 속성대로 지정되도록 width:auto를 사용해 보면 아래와 같습니다. 


```html
<style>
 div,p, span { width:auto; background-color: red;}
</style>
<div>div</div>
<p>p</p>
<span>span</span>
```
여기에서 div의 width를 400px로 하면 너비가 줄어듭니다. 같은 내용을 span태그에 적용하면 크기에 변화가 없습니다. 이유는 span 태그는 인라인 속성으로 width를 따로 지정할 수 없기 때문입니다.  
여기에 내용에 맞춰 크기를 지정하고자 한다면 즉, 우리가 일일히 너비를 정확히 알 수 없으니 내용에 있는만큼 너비를 지정하고자 할때 min-content, max-content를 사용할 수 있습니다.  

위의 예제에서 lorem의 긴문자를 내용으로 삽입해보면 어찌될까요? 
## width: min-content, max-content   
min-content는 요소의 너비를 줄일 수 있을만큼 줄이기 때문에 한 단어의 크기만큼만 너비가 지정됩니다.
반대로
max-content는 요소의 너비를 가장 긴 문장에 맞춥니다.
```html
<div>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestiae, <br>
illum ipsam! Ipsa quos placeat natus facilis, possimus architecto? Eaque delectus deserunt dolores, distinctio  <br> cumque assumenda! Nam qui nulla dolor! Libero.</div>
<p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Inventore doloribus culpa, ut commodi explicabo incidunt vel nesciunt, sequi voluptatibus, in consectetur perferendis! Et blanditiis, nisi quis delectus rem hic facilis?</p>
<span>Lorem ipsum dolor sit amet consectetur adipisicing elit. At possimus autem eligendi doloribus molestias reiciendis molestiae distinctio incidunt nam quos, quisquam officiis cum, maiores, amet vero itaque nostrum perspiciatis sapiente.</span>
```
위의 코드에서 
1. div태그안에 여러개의 br 태그를 삽입했을때(여기서는 3줄) 가장 긴 문장의 길이가 너비가 됩니다.  
2. p태그안에는 줄바꿈 기호가 없기 때문에 한줄로 쭈욱 되고요
3. span 태그는 어찌되나면, 결과화면 브라우저의 너비를 조정해보면 브라우저의 크기에 따라 자동으로 줄을 바꾸면서 너비를 조정합니다. 

## width : fit-content 
auto + max-content의 하이브리드 형입니다. 위의 긴 문장에 width:fit-content로만 바꾸면 p 태그에 변화가 생깁니다. p태그의 내용이 가로 방향으로 한 줄로 쭈욱 되었던것이 브라우저의 오른쪽 끝에서 자동 줄바꿈이 일어납니다.  
다른 div, span는 이전과 동일하게 작동합니다.   


## 쓰기모드와 함께 사용할때는 
1. inline-size : 쓰기모드가 수평일때는 요소의 폭을 정의, 쓰기모드가 수직일때는 요소의 높이를 정의한다.
2. block-size 라는 것이 또 있습니다.

```html
<style>
   .elem { 
       /* writing-mode: vertical-lr;  */
       inline-size: 400px;
       background-color: orange;  }
 </style>
<div class="elem">Lorem ipsum dolor sit amet, consectetur adipisicing elit.
 Nemo, laboriosam eveniet? Illo voluptas repellendus ve
ritatis possimus doloribus </div>
```


위의 예제에서 쓰기모드가 수직일지라도 .elem의 너비를 400px로 유지하고 싶다면 다른 방식으로 이렇게 해 볼 수도 있다. 
```html
 <style>
     html{writing-mode: vertical-lr;   }
     p { width: 400px; background-color:MediumTurquoise; }
 </style>
```
p태그에 크기는 그냥 width를 지정했다.







