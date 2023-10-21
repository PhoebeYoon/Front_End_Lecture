##### 🍑  Front_End 과정 1단계 

## canvas
```html
 <h1>Canvas Drawing</h1>
 <canvas id="canvas" width="600"  height="600"> </canvas>
<script>    
let canvas =  document.querySelector('canvas') 
const ctx = canvas.getContext('2d')
    
//fillRect()
ctx.fillStyle="red"
ctx.fillRect(20,20,100,100)
ctx.fillStyle="blue"
ctx.fillRect(130,20, 150,100)


// strokeRect()
ctx.lineWidth =5;
ctx.strokeStyle='green'
ctx.strokeRect(100,200, 150,150)

//clearRect(0)
ctx.clearRect(25,25, 140,90)

// fillText()
ctx.font= "20px Arial"
ctx.fillStyle="magenta";
ctx.fillText("Nice to see you", 400,500)

// stokeText()
ctx.lineWidth=1;
ctx.fillStyle="orange";
// ctx.fillText('Are you with me', 400,100)
ctx.strokeText('Are you with me', 400,100)
</script>
```  
> 위의 태그 그대로 사용한다.   
```html
ctx.beginPath()
ctx.moveTo(50,50)
ctx.lineTo(150,50)
ctx.lineTo(150,150)
ctx.lineTo(50,150)

//ctx.lineTo(50,50) 이렇게 첫번째 좌표로 돌아가는대신 closePath()를 한다
ctx.closePath()

// ctx.fillStyle="pink"
// ctx.strokeStyle="blue"
// ctx.lineWidth="3"

ctx.fill()  // 특별히 지정하지 않으면 검정색으로 칠해짐
ctx.stroke();
```
> 위의 태그 그대로 사용한다.
```html
tx.beginPath()
ctx.moveTo(50,50)
ctx.lineTo( 150, 50);
ctx.lineTo(100,200);
ctx.lineTo(50,50);
ctx.fillStyle="coral"
ctx.fill()

ctx.beginPath()
ctx.moveTo(200,50)
ctx.lineTo(150, 200)
ctx.lineTo(250, 200)
ctx.closePath()
ctx.stroke();

ctx.beginPath();
ctx.rect(300,50, 150, 100)
ctx.fillStyle="teal"
ctx.fill();

```








