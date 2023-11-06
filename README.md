##### 🍑  Front_End 과정 1단계 


## intersectionObserver를 사용하는 이유 [javascript 레포지토리 참조]

scroll 이벤트는 성능에 악영향을 줄 수 있는데 스크롤시 짧은 시간 내에 수 백, 수 천의 이벤트가 동기적으로 실행될 수 있습니다. 그리고 페이지 내에 각 요소가 각기의 목적(광고, 레이지 로딩, 무한 스크롤 등)의 이유로 scroll 이벤트를 리스닝하기 때문에 이에 상응하는 콜백이 무수히 실행될 수 있습니다. 이는 메인 스레드에 큰 부하를 줄 수 있습니다.    

그리고 getBoundingClientRect 은 reflow를 발생시킬 수 있습니다. 본래 브라우저는 최적화를 위해 필요한 여러 작업을 묶어 큐에 쌓아 대기하다가 한 번의 reflow 로 처리하고자 합니다. 그러나 getBoundingClientRect 호출시 값(top, right 등)을 정확히 읽어들이기 위해 큐를 flush하고 스타일을 적용함으로써 다 수의 reflow 를 발생시킬 수 있습니다.     
Intersection Observer API 는 루트 요소와 타겟 요소의 교차점을 관찰합니다. 그리고 타겟 요소가 루트 요소와 교차하는지 아닌지를 구별하는 기능을 제공하고 있습니다. scroll 이벤트와 다르게 교차 시 비동기적으로 실행되며 가시성 구분 시 reflow 를 발생시키지 않습니다. 여러모로 성능 상 유리합니다.

설명 출처 : https://velog.io/@elrion018/실무에서-느낀-점을-곁들인-intersection-Observer-API-정리 


## data-속성 / intersectionObserver 함께 사용해서
https://www.youtube.com/watch?v=-pDPASqX97w 의 내용을 따라한것이며 주석의 내용은 본인입니다  

```html
  <style>
    .full-screen-section {    position: relative;}
    [data-img-to-show] {
        position: absolute;
        top:20%;
        width: 100%; height: 10px;
        background-color: red;  }
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
js를 아래와 같이 수정한다.   (css도 바뀝니다. 첨부된 파일에서 참조)   

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




