##### 🍑  Front_End 과정 1단계 

## Bézier curve
참고 ) https://developer.mozilla.org/en-US/docs/Glossary/Bezier_curve     

```html
   <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {margin: 0;}
        canvas { border:1px solid;
             box-shadow: 1px 1px 3px rgba(0,0,0,0.3);}
    </style>
</head>
<body>
    <h1>Canvas </h1>
    <button onclick="clear()">지우기</button> 
    <br>
    <canvas id="draw" width="800" height="800"></canvas>
   
    <script>
const canvas = document.querySelector('#draw');
const ctx = canvas.getContext('2d');
const btn = document.querySelector('button')
canvas.width = window.innerWidth*0.8;
canvas.height = window.innerHeight*0.8;
ctx.strokeStyle = '#BADA55';
ctx.lineJoin = 'round';
ctx.lineCap = 'round';
ctx.lineWidth = 100;
// lineCap = round해야 둥근모양이 나타나면서 끊어지지 않는다


let isDrawing = false;
let lastX = 0;
let lastY = 0;
let hue = 0;
let direction = true;


// function draw1(){
//     ctx.strokeStyle=`hsl(100%, 100%, 50%)`;
//     ctx.beginPath();
//     ctx.moveTo(100,100);  // start From
//     ctx.lineTo(110,110)    // go to
//     ctx.stroke();
// }
// draw1();


function draw(e){
    if (!isDrawing) return;
    ctx.strokeStyle=`hsl(${hue}, 100%, 50%)`
    ctx.beginPath();
    
    ctx.moveTo(lastX, lastY)
    //  console.log(e.offsetX, e.offsetY)
    ctx.lineTo(e.offsetX, e.offsetY)
    ctx.stroke();
    [lastX, lastY] = [e.offsetX, e.offsetY];
    hue++;
    console.log("hue : ", hue)
    if (hue >= 360) {
        hue = 0;
    }
    if (ctx.lineWidth >= 100 || ctx.lineWidth <= 1) {
    direction = !direction;
  }

  if(direction) {
    ctx.lineWidth++;
  } else {
    ctx.lineWidth--;
  }
}

// 마우스가 놓여진 그 위치에서 시작하도록 한다
canvas.addEventListener('mousedown', (e)=>{
    isDrawing = true;
    [lastX, lastY]=[e.offsetX, e.offsetY]
})

canvas.addEventListener('mousemove', draw);
// 마우스를 떼거나 영역밖으로 나갔을때 draw함수의 실행을 멈춘다
canvas.addEventListener("mouseup" ,()=> isDrawing=false);
canvas.addEventListener("mouseout" ,()=> isDrawing=false);
// 캠퍼스를 clear한다
btn.addEventListener('click', ()=>{ 
    ctx.clearRect(0, 0, canvas.width, canvas.height);
})

    </script>
</body>
</html>

```





