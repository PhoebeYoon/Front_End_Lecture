##### 🍑  Front_End 과정 1단계 

## 특정클래스의 순서를 선택할때 

```html
 <style>
 * {font-size: 20px;}
.red { color:red}
/* .list li:nth-child(5) { text-decoration: underline; color:green} */
.list :nth-child(5) { color:green}
.list :nth-child(5)  { text-decoration: underline;}

/* .list .red:nth-child(2 ) { text-decoration: line-through;} 적용되지 않는다  아래설명참조*/
.list :nth-child(2 of .red){ text-decoration: line-through;}
.list :nth-child(2n+1 of .red){ font-weight: 900;}
    </style>
<body>
    <ul class="list">
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
        <li>item</li>
        <li class="red">item</li>
        <li>item</li>
    </ul>
</body>
```
위의 내용에서  "언급된 설명"처럼 ``` .list .red:nth-child(2 ) { text-decoration: line-through; ```은 적용되지 않는다   
list클래스 아래에 있는 red클래스에서 2번째것만 바꾸고 싶다면   
```  .list :nth-child(2 of .red){ text-decoration: line-through;}  ``` 와 같이 언급해주어야 한다. 또한     
``` .list :nth-child(2n+1 of .red){ font-weight: 900;}  ``` 와 같이 짝수, 홀수와 같은 표현을 사용할 수도 있다.   


## 테이블에서 행의 show/hide 여부에 따라 클래스를 적용하기

```html
   <style>
        td,th { border: 1px solid; padding: 0.5em;}
        table tr:nth-child(even) {  background-color: #ddd; }
        /* table tr:nth-child(even of :not(.hidden)) { background-color: #ddd;   } 이렇게 바꿔보자*/
        tr.hidden { display: none;}
    </style>
</head>
<body>
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
                <th>show/Hide</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>John</td>
                <td>25</td>
                <td><button> Hide</button></td>
            </tr>
            <tr>
                <td>Smith</td>
                <td>32</td>
                <td><button> Hide</button></td>
            </tr>
            <tr>
                <td>Peter</td>
                <td>27</td>
                <td><button> Hide</button></td>
            </tr>
            <tr>
                <td>Mark</td>
                <td>30</td>
                <td><button> Hide</button></td>
            </tr>
        </tbody>
    </table>
    <script>
        let btns = document.querySelectorAll('button')
        btns.forEach( (btn)=>{ 
            btn.addEventListener('click', (e)=>{
                //console.log(e.target.parentElement.parentElement)
              let b = e.target.parentElement.parentElement;
              // b.style.backgroundColor="red"
              b.classList.add('hidden')
            }
            )
        } )
    </script>

```




