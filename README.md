##### 🍑  Front_End 과정 1단계 

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
