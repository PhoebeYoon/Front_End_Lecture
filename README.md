##### 🍑  Front_End 과정 1단계 


## data-속성 / intersectionObserver 함께 사용해서

```html
  <style>
        .full-screen-section {
        position: relative;}

        [data-img-to-show] {
            position: absolute;
            top:20%;
            width: 100%; height: 10px;
            background-color: red;
  
        }
        img[data-img] { display: none;}
        .show { display: block;}
        .bg { background-color: green;}
    </style>
<div class="imgs">
        <img src="https://placehold.co/300x200/orange/white" data-img  id="img-1">
        <img src="https://placehold.co/300x200/gold/000000"  data-img  id="img-2">
        <img src="https://placehold.co/300x200/teal/white"   data-img  id="img-3">
        <!--   data-img 속성은 일괄적으로 가져오기 위해 임의로 만듦.  -->
</div>
    
    <section class="full-screen-section">
        <h1>full Stack</h1>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Cumque, incidunt!</p>
        <div data-img-to-show="#img-1" ></div>
    </section>
    <section class="full-screen-section">
        <h1>full Stack</h1>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Cumque, incidunt!</p>
        <div data-img-to-show="#img-3" ></div>
    </section>
    <section class="full-screen-section">
        <h1>full Stack</h1>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Cumque, incidunt!</p>
        <div data-img-to-show="#img-3" ></div>

    </section>

    <script>
const observer = new IntersectionObserver(entries =>{
    for( let i=entries.length-1; i>=0 ; i--){
        const entry = entries[i]
        // console.log(entry.target.id)
        if( !entry.isIntersecting) {
            console.log(entry.target.getAttribute('src'))  // 속성을 읽어오는지 점검
            entry.target.setAttribute('style',"display:block;")
                          // 기존 css을 변경, none-> block 수정
         }
     }
})
    document.querySelectorAll('[data-img]').forEach(section=>{
            observer.observe(section)
    })  
    </script>
```
js를 아래와 같이 수정한다.   

```js
window.addEventListener("scroll", setScrollVar)
window.addEventListener("resize", setScrollVar)
function setScrollVar(){
    const htmlElement = document.documentElement ;
    const percentOfScreenHeightScrolled = htmlElement.scrollTop / htmlElement.clientHeight;
    htmlElement.style.setProperty(
    "--scroll" ,
        Math.min( percentOfScreenHeightScrolled*100, 100)
    )
}
setScrollVar()
const observer = new IntersectionObserver(entries =>{ 
    for( let i= entries.length-1; i>=0; i--){
        const entry = entries[i]
        if( entry.isIntersecting){
            document.querySelectorAll("[data-img]").forEach( img=>{
                // console.log(img)
                img.classList.remove('show')
            })
     //let x = entry.target.dataset.imgToShow; // imgToShow 는 <div data-img-to-show ~ >에서
                                              // data- 를 빼고 js에서 변환시킨 이름이다.
                                    // 카멜케이스방식으로 이름을 변경한다. 그래서 imgToShow가 된것이다
     //console.log(x) // 출력: #img-1 

        const img= document.querySelector(entry.target.dataset.imgToShow)
        img.classList.add("show")
        break
        }
    }
})
document.querySelectorAll("[data-img-to-show]").forEach(section =>{
    observer.observe(section)
})
</script>
``` 
위의 내용에서  ```  <div data-image-visible="#img-3" ></div>``` 변경하면 기존의 코드는 작동되질 않는다   
```js
const img= document.querySelector(entry.target.dataset.imageVisible)
document.querySelectorAll("[data-image-visible").forEach(section =>{
    observer.observe(section)
})
이 부분들 바꿔야 한다 
```




