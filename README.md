##### 🍑  Front_End 과정 1단계 


이미 절대단위와 상대단위에 대해 학습하셨죠?  이번에는 em, rem에 대해 다룹니다.  
px는 절대단위이고 em, rem은 모두 상대적 단위로 크기를 계산할때 그 **기준이 다를뿐입니다.**    


em는 부모가 기준이고,   
rem는 루트(root)가 기준입니다. ( rem의 r은 root를 말합니다)    
여기서 말하는 루트란  css에서 ``` html {  font-size: 16px } ``` 로 지정해 줍니다.   
그러니까 rem은 상대적인 단위로써,  기준을 16px로 했다가 14px로 바꾼다면 rem단위를 가진 것들은 모두 크기가 바뀐다는 의미입니다.    


em, rem은 글자의 크기를 정할때만 사용하는 것이 아니라 width, height 등 여러군데 사용할 수 있습니다.    


그리고 여기서는 rem를 주로 다룰 예정입니다.   
왜냐하면 em의 기준이 부모이기 때문에 nested 구조에서 em를 사용하면 안쪽에 있는 것들은 점점 작아지거나 점점 커지기 때문에 이를 보완하기 위해 rem이 나온것입니다.  
### calc() 는 value이고 length 와 숫자(numeric thing)관련해서 사용된다. 

```css
.el {
  font-size: calc(3vw + 2px);
  width:     calc(100% - 20px);
  height:    calc(100vh - 20px);
  padding:   calc(1vw + 5px);
}

.el {
  margin: 10px calc(2vw + 5px);
  border-radius: 15px calc(15px / 3) 4px 2px;
  transition: transform calc(1s - 120ms);
}

```
> calc()는 문자관련해서는 사용하지 않으며 media query에도 사용하지 않는다.   

### mixing units 
```css
transform: rotate(calc(1turn + 45deg));
animation-delay: calc(1s + 15ms);
```
### + , - 사용
```css
.el {
  /* 오케이 */
  margin: calc(10px + 10px);
  margin: calc(20px - 10px);
  margin: calc(30px / 3); // 나누기에는 단위가 필요없다
  margin: calc(10px * 3); //곱하기(*)를 위해서는 숫자 중 하나가 단위가 없어야한다.
  margin: calc(3 * 10px);

  /* 노 오케이 */
  margin: calc(10px + 5);
  margin: calc(20px + 10);
  margin: calc(30px * 3px);
}

```

### 기호 양옆에 공백넣기 

```css
/* 오케이 */
width: calc(
    100%     /   3
  );

/* 노 오케이 */
font-size: calc(3vw-2px); // - 기호 양옆에 공백추가해야 한다
font-size: calc(3vw+2px);

```

### 연산자 우선순위에 따라 
```css
.el {
  width: calc(100% / 3 - 1rem * 2);  // 연산자 우선순위에 따라 계산
  width: calc((100% + 2rem) / 2); // 연산자 우선순위에 따라 계산
}
```   
### 사용자지정 속성에도 사용할 수 있다.    

```css
html {
  --spacing: 10px;
}
.module {
  padding: calc(var(--spacing) * 2);
}
```



