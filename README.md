##### 🍑  Front_End 과정 1단계 

## border-block
border 속성값을 설정한다. writing-mode에 따라 결과가 달라진다.   
border-block는 아래의 속성과 함께를 축약한 것이다.  
- border-block-color    
- border-block-style    
- border-block-width    

#### writing-mode 와 함께 사용할것
```html
<style>
body {
  display: flex;
  align-items: flex-start;
  flex-wrap: wrap;
  gap: 2em;
  padding: 2em;
}

.box {
  background: #eaeaea;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  flex-basis: 17%;
  height: 200px;
}

.box1{
  border-block: 5px solid red;
  writing-mode: horizontal-tb;
}

.box2{
  border-block: 5px solid red;
  writing-mode: vertical-lr;
}
</style>
<div class="box box1">
  Horizontal-tb
</div>
<div class="box box2">
  Vertical-lr
</div>

```
