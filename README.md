##### 🍑  Front_End 과정 1단계 

## resize  
요소의 크기를 조정할 수 있는지 여부와 조정할 수 있는 경우 어느 방향으로 설정합니다

```html
<style> 
div {
  border: 2px solid;
  padding: 20px; 
  width: 300px;
  
   resize:horizontal;  
   overflow: auto;
   /* overflow:auto 또는 scroll 를 설정해줘야 한다.  */
   /* resize:vertical;  */
   /* resize:none; */
   /* resize: both; */
  
}
</style>
<div>
  <p>Let the user resize both the height and the width of this div element.</p>
  <p>To resize: Click and drag the bottom right corner of this div element.</p>
</div>
```

resize:none는 사이즈를 조정할 수 없게 한다.  
