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
// Triangle
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

// Rectangle
ctx.beginPath();
ctx.rect(300,50, 150, 100)
ctx.fillStyle="teal"
ctx.fill();

```

```js

// arc(x, y, radius, startAngle, endAngle)
// arc(x, y, radius, startAngle, endAngle, counterclockwise)

ctx.beginPath()
ctx.arc(75, 75, 50, 0, Math.PI*2, true)
ctx.moveTo(110, 75)
ctx.arc(75, 75, 35, 0, Math.PI, false)

ctx.moveTo(65,65)
ctx.arc(60,65,5,0, Math.PI *2, true)
ctx.moveTo(96, 65)
ctx.arc(90,65,5,0, Math.PI *2, true)
ctx.stroke();


// Big face
ctx.beginPath()
const centerX = canvas.width/2
const centerY = canvas.height/2

ctx.arc(centerX, centerY, 200, 0, Math.PI*2, true)

ctx.moveTo(centerX +100, centerY)  // mouse
ctx.arc(centerX, centerY, 100, 0, Math.PI , false)

ctx.moveTo(centerX -60, centerY -80) //left eye
ctx.arc(centerX -80, centerY-80, 20, 0 , Math.PI*2)

ctx.moveTo(centerX+100, centerY -80) // right eye
ctx.arc(centerX +80, centerY-80, 20, 0 , Math.PI*2)

ctx.stroke()

```








