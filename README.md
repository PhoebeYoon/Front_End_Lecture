##### 🍑  Front_End 과정 1단계 

## @scope 
scope 라는 영어는 
"명사 (주제·조직·활동 등이 다루는) 범위" 이다.  새로운 브라우저에서만 작동한다. 기존에 css에서 어떤 엘리먼트를 특정하기 위해 계층구조로 적어야했던 것을 간단히 언급할 수 있게 되었다.

``` html
// 기존의 css방식은 아래와 같다.
<style>
.card { background: white;    border:1px solid;
         padding: 0.5rem;}
.title { color:green}
.card .title { color:red}
</style>
<h1 class="title">Article Title</h1> 
<div class="card">
        <div class="title">Red Card Title</div>
        <div class="body">
            Lorem, ipsum dolor.
            <div class="title">Body title</div>
        </div>
    </div>

```

``` html
// scope를 사용해서 
<style>
.card { background: white;    border:1px solid;
         padding: 0.5rem;}
.title { color:green}
 @scope ( .card){
     .title {color:red };
   }
@scope (.card) to (.body){
  /*  위 내용의 to 의 의미는  .card 안에 있지만 .body전까지 의미 */
  .title { color:blue}
 }
</style>
 <div class="header">
     <style>
       @scope {
          .title {  text-decoration : underline}
      }
     </style>
      <h1 class="title">Article Title</h1>
</div>
<div class="card">
    <div class="title">Red Card Title</div>
    <div class="body">
        Lorem, ipsum dolor.
        <div class="title">Body title</div>
    </div>
</div>
```
와 같다.  
