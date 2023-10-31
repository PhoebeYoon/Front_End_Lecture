##### 🍑  Front_End 과정 1단계 


## infinite horizontal scroll
```html
<style>
        :root {
            --clr-neutral-100 :hsl(0,0%, 100%);
            --clr-primary-100 :hsl(205, 15%, 58%);
            --clr-primary-400 :hsl(215, 25%, 27%);
            --clr-primary-800 :hsl(217, 33%, 17%);
            --clr-primary-900 :hsl(218, 33%, 9%);
        }
        html { color-scheme: light}
        body { display: grid; 
            min-block-size: 100vh;
            place-content: center;
            font-family: system-ui, sans-serif;
            font-size: 1.125rem;
            background-color: var(--clr-primary-800);
            } 

        .tag-list { margin: 0; padding-inline: 0; list-style: none;}
        .tag-list li { padding: 1rem;  
            background:var(--clr-primary-400);
            border-radius: 0.5rem;
            box-shadow: 0 0.5rem 1rem -0.25rem var(--clr-primary-900);
        }
        .scroller { max-width: 600px; 
          /* outline: 3px solid lime; */
        }
        .scroller__inner{
            padding-block: 1rem;
            display: flex; 
            flex-wrap: wrap;
            gap:1rem;
         }

  .scroller[data-animated="true"] {
    overflow: hidden;
    /* -webkit-mask:linear-graident(90deg, transparent, white 20%, 
        white 80%, transparent);
    mask: linear-graident(90deg, transparent, white 20%, 
        white 80%, transparent);   */
    }
.scroller[data-animated="true"] .scroller__inner {
    width: max-content;
    flex-wrap: nowrap;
    animation: scroll var(--_animation-duration, 40s) var(--_animation-direction, forwards) linear infinite;
}

.scroller[data-direction="right"] {
   --_animation-direction:reverse
}

.scroller[data-direction="left"] {
   --_animation-direction:forwards;
}

.scroller[data-speed="fast"] {
   --_animation-duration:20s
}
.scroller[data-speed="slow"] {
   --_animation-duration:60s
}

@keyframes scroll {
  to {
     transform: translate(calc(-50% - 0.5rem));}
  }
</style>
<h1>Infinite Scroll Animatiion</h1>
  <div class="scroller" data-direction="left" data-speed="fast" >
    <ul class="tag-list scroller__inner">
        <li>html</li>
        <li>css</li>
        <li>js</li>
        <li>ssg</li>
        <li>webdev</li>
        <li>animation</li>
        <li>ui/ux</li>
        <li>webdev</li>
        <li>animation</li>
        <li>ui/ux</li>
    </ul>
  </div>
  <div class="scroller" data-direction="right" data-speed="slow">
    <ul class="scroller__inner">
        <img src=https://placehold.co/300x200/orange/FFF"" alt="">
        <img src=https://placehold.co/300x200/pink/FFF"" alt="">
        <img src=https://placehold.co/300x200/teal/FFF"" alt="">
        <img src=https://placehold.co/300x200/gold/FFF"" alt="">
        <img src=https://placehold.co/300x200/cyan/FFF"" alt="">
        <img src=https://placehold.co/300x200/green/FFF"" alt="">
    </ul>
  </div>
<script>
    const scrollers = document.querySelectorAll('.scroller')
    console.log(window.matchMedia("(prefers-reduced-motion:reduce)").matches)

    if( ! window.matchMedia("(prefers-reduced-motion:reduce)").matches) {
        addAnimation()
    }
  function addAnimation(){
    scrollers.forEach( (scroller)=>{
        scroller.setAttribute("data-animated", true);
        const scrollerInner = scroller.querySelector('.scroller__inner');
        const scrollerContent = Array.from(scrollerInner.children)

        scrollerContent.forEach( (item)=>{
            const duplicatedItem = item.cloneNode(true);
            duplicatedItem.setAttribute('aria-hidden', true)
            scrollerInner.appendChild(duplicatedItem )
        })
    })
}
  </script>
```



출처 : https://codepen.io/kevinpowell/pen/BavVLra
