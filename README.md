##### 🍑  Front_End 과정 1단계 


## classList 이렇게도 사용해 봅시다.

```html
 <style>
.foo { width: 100px; height: 100px; background-color: orange;}
.visible { border:3px solid}
    </style>
<body>
    <script>
const div = document.createElement("div");
div.className = "foo";
console.log(div.outerHTML);

div.classList.remove("foo");
div.classList.add("anotherclass");
console.log(div.outerHTML);

div.classList.toggle("visible");
console.log(div.outerHTML);
// 변수의 값에 따라 클래스를 toggle 한다
let i=1;
div.classList.toggle('visible', i<10) 👋🏻
console.log('i가 1일때  ',div.outerHTML);


console.log(div.classList.contains("foo"))
// 여러개의 클래스를 추가, 삭제
div.classList.add('foo','bar','baz')
div.classList.remove("foo", "bar", "baz");


const cls = ["foo", "bar"]; 
div.classList.add(...cls)  👋🏻
console.log(div.outerHTML)
div.classList.remove(...cls);

// 클래스를 교체한다
div.classList.replace("foo", "bar");
console.log(div.outerHTML)
    </script>

```


