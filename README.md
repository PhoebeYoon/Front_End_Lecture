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


