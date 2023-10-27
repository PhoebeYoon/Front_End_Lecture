##### 🍑  Front_End 과정 1단계 

## removeEventListener 이벤트

```html
  <style>
        @import url("https://fonts.googleapis.com/css?family=Lato:400,400i,700");
body {
  height: 100vh;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background: radial-gradient(#666, #222);
}

.module-jamf {
  width: 300px;
  border: 1px solid white;
}

.jamf-container {
  display: block;
  width: 300px;
  height: 300px;
  overflow: hidden;
}

.jamf-mover {
  width: 300px;
  height: 300px;
  background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/3/jamf-laptop-screen.png);
  background-size: 800px;
  background-repeat: no-repeat;
  background-position: -30px 40px;
  transform: scale(1);
  transition: background-position 0.25s;
}
.jamf-mover.no-more-slidey {
  transition: none;
}

.interlude {
  background: white;
  padding: 1rem;
  font: 12px "Lato";
}
  </style>
<div class="module-jamf" id="module-jamf">
       <a href="http://synd.co/2DNywdE" class="jamf-container" id="jamf-container" target="_blank" rel="noopener">
          <div class="jamf-mover" id="jamf-mover"></div>
       </a>      
     <div class="interlude"> 마우스를 움직여 내용을 확인하세요    </div>
</div>
<script>
let container = document.querySelector("#jamf-container");
let mover = document.querySelector("#jamf-mover");

container.addEventListener("mousemove", function(e) {
  mover.style.backgroundPositionX = -e.offsetX * 1.8 + "px";
  mover.style.backgroundPositionY = -e.offsetY + 80 + "px";
});
// const fun1= function example(){
//   setTimeout( mover.classList.add("no-more-slidey"), 250) ;
// }
// container.addEventListener("mouseenter", fun1);
// container.removeEventListener("mouseenter", fun1);

container.addEventListener("mouseenter", 
   function example(){
      setTimeout( mover.classList.add("no-more-slidey"), 250) ;
  } );
container.removeEventListener("mouseenter", fun1);
</script>
```
> 위의 스크립트는 마우스가 움직여서 영역밖으로 나가면 이미지로 함께 그 위치를 바꾸어 오히려 이미지를 사라지는 것처럼 보이기 때문에 no-more-slidey 클래스를 추가하고, mouseenter이벤트가 다시 처음부터 발생하는 것을 방지한다. 왜냐하면 마우스를  계속 움직이는 것이지 다시 처음부터 시작하는 것이 아니기 때문이다
또한 addEventListener와 마찬가지로 이벤트를 제거하기 위해 removeEventListener를 실행하지만 이것은 이 두 이벤트를  ===  했을때 결과가 true일때만 동일 이벤트를 제거할 수 있다. 그래서 setTimeout함수를 따로 작성했다. 

예제참고 ) https://css-tricks.com/moving-backgrounds/

