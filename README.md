##### 🍑  Front_End 과정 1단계 

## @property

자바스크립트를 실행할 필요없이 스타일 시트에서 직접 사용자 지정 속성 등록을 나타낸다. 유효한 @property 규칙은 자바스크립트의 registerProperty()가 동등한 매개변수로 호출된 것처럼 사용자 정의 속성을 등록한다.

@property는 CSS 변수의 초기값, 유형, 상속 여부를 선언할 수 있다.  
```html  
   <style>
@property --primary {
 syntax: '<color>';
 initial-value: orange;
 inherits: true;
}
.text-1 { color:var(--primary)}
.text-2 { 
      /* --primary:green;  */ --primary:#ff;
     color:var(--primary)}

    </style>
<h3>1. CSS 변수 사용하기</h3>
<span class="text-1">CSS Variables</span><br/><br/>

<h3>2. 변수에 타입에 맞지 않는 값을 할당한 경우, 초기값을 사용</h3>
<span class="text-2">CSS Variables</span>

```
위의 예제에서  .text-2에 --primary를 다시 green으로 정의하며 재 정의된 색상으로 나오지만 타입에 맞지 않게 (#ff) 으로 정의되면 기존에 정의된 내용을 실행한다.  

만약에 위의 내용을 자바스크립트로 사용하고자 한다면 registerProperty() 를 사용하면 된다.  
```
window.CSS.registerProperty({
   name: '--primary',       // 변수명
  syntax: '<color>',       // 변수값 유형
  initialValue: 'orange',  // 초기값
  inherits: true,          // 상속여부
})
```
위의 예제를 다시 적으면, 
```html
    <style>
.text-1 { color:var(--primary)}
.text-2 {  --primary:green;  color:var(--primary)}
    </style>
<h3>1. CSS 변수 사용하기</h3>
<span class="text-1">CSS Variables</span><br/><br/>

<h3>2. 변수에 타입에 맞지 않는 값을 할당한 경우, 초기값을 사용</h3>
<span class="text-2">CSS Variables</span>
<script>
    window.CSS.registerProperty({
    name:'--primary',
    syntax :'<color>',
    initialValue:'blue',
    inherits: true
    })
</script>
```
또한,
자바스크립트에서 정의한 값을  재정의해서 사용하고자 한다면 스타일에서 값을 바꾸어야 한다. 
``` document.documentElement.style.setProperty('--primary','gold')```
주의할 것은 CSS.registerProperty()가 아니라 .style.setProperty() 이다.





