##### 🍑  Front_End 과정 1단계 


## inset 

The inset CSS property is a shorthand that corresponds to the top, right, bottom, and/or left properties.
It has the same multi-value syntax of the margin shorthand.   
```inset: 10px 30% 20px 0; ``` 방향은 top, right, bottom , left 순으로 시계방향이다.  

[예제]

```html
    <style>
div { background-color:gold;
    width: 150px;   height: 120px;
    /* position: relative; */
}
.exampleText { 
 position: fixed; // 위의 div의 position이 살아 있다면 여기있는 position:fixed는 작동하지 않는다
 position: absolute; inset : 20px 40px 30px 10px;  // 음수를 입력할 수도 있다. 
 background-color: #c8c800;
     }
    </style>
<div>
        <span class="exampleText">Example text</span>
</div>

```
