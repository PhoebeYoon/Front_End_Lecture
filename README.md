##### 🍑  Front_End 과정 1단계 


## 튕기는 공

```html
<h1>그림을 그려봅시다</h1>
<canvas id="draw" width="800" height="600"></canvas>
<script>
const canvas = document.querySelector('#draw');
const ctx = canvas.getContext('2d');
const circle = {
    x : 200,
    y:200,
    size:30,
    dx : 5,
    dy : 4
}

function drawCircle(){
    ctx.beginPath();
    ctx.arc(circle.x, circle.y, circle.size, 0, Math.PI*2)
    ctx.fillStyle="purple"
    ctx.fill();
}

function update(){
    ctx.clearRect(0,0,canvas.width, canvas.height)
   drawCircle();
    circle.x += circle.dx; // 위치바꾸기 x축으로 이동
    requestAnimationFrame(update) // requestAnimationFrame()는 콜백기능을 사용한다
}
// drawCircle()
update();
    </script>

```
이제 여기에 상하좌우에 다닿으면 반대편으로 이동하도록 하여 마치 튕기는 것처럼 해봅시다.


```html

<script>
const canvas = document.querySelector('#draw');
const ctx = canvas.getContext('2d');
const circle = {
    x : 200,
    y:  200,
    size:30,
    dx : 5,
    dy : 4
}

function drawCircle(){
    ctx.beginPath();
    ctx.arc(circle.x, circle.y, circle.size, 0, Math.PI*2)
    ctx.fillStyle="red"
    ctx.fill();
}

function update(){
       ctx.clearRect(0, 0, canvas.width, canvas.height);
     drawCircle();
     circle.x += circle.dx; // 위치바꾸기 x축으로 이동
     //circle.y += circle.dy;
    
     if(   ( circle.x + circle.size > canvas.width) || ( circle.x -circle.size)< 0) {
        circle.dx *= -1;
    }

    if(   ( circle.y + circle.size > canvas.height) || ( circle.y -circle.size)< 0) {
        circle.dy *= -1;
    }

  requestAnimationFrame(update) // requestAnimationFrame()는 콜백기능을 사용한다
}
update();
    </script>
```





