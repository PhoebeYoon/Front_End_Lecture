##### 🍑  Front_End 과정 1단계 

## what is font variant

글꼴의 변형에 사용됩니다. 
css font-variant 속성은 글꼴의 small-caps 또는 노멀을 정의할 수 있습니다. 결과는 같은 글자크기이지만 대문자로 출력된다.   
속성값은 normal / small-cpas /inherit 
```html

 <style>
        span.normal { font-variant: normal; }
        span.smallCaps { font-variant: small-caps; }
        p.normal { font-variant: normal }
        p.smallCaps { font-variant: small-caps; }
    </style>
<body>
    <span class="normal">span</span>
    <span class="smallCaps">span</span>
    <p class="normal">lorem.</p>
    <p class="smallCaps">lorem</p>
</body>
```
> **글리프(glyph)** ,
 글자의 모양을 가리킨다. 글꼴마다 독창적인 글자 모양을 갖는 것은 글리프(glyph)가 존재하기 때문이라고 할 수 있다.

> **대체 글리프(glyph)**,
대체 글리프(glyph)은 해당 글꼴에서 기본적으로 보여지는 글자 모양이외에 추가적으로 제공되는 글자 모양을 의미한다. 물론 모든 글꼴이 기술적으로 대체 글리프(glyph)를 지원하는 것은 아니다. 기술적으로 대체 글리프(glyph)가 가능한 글꼴의 포맷은 OpenType이다. OpenType 포맷의 글꼴이라고 해서 대체 글리프(glyph)를 모두 가지고 있는 것은 아니다. 글꼴 개발자가 추가적인 글리프(glyph)를 지원해야 한다
대체 글리프(glyph)는 OpenType 포맷이 가지고 있는 기능(feature)이라는 메커니즘을 사용한다. 이 기능(feature)을 통해 다양한 지원을 하고 있고 대체 글리프(glyph)도 해당된다. 대체 글리프(glyph)는 글꼴 개발자가 정한 태그를 사용해서 글리프(glyph)를 선택하는 인덱스를 지정한다

참고 :  http://www.devdic.com/css/reference/properties/css-property:6200/font-variant-alternates



## font-variant-alternates란
font-variant-alternate 속성은 일반적으로 페이지에서 텍스트의 모양을 개선할 수 있는 다양한 글꼴 관련 기능을 활성화하기 위해 사용되는 CSS3 속성 중 하나입니다. font-variant-alternate 속성은 대체 글리프를 구체적으로 선택하는 데 사용됩니다. 임의의 주어진 문자에 대해 해당 문자의 기본 글리프 외에 글꼴로 다양한 대체 글리프를 제공할 수 있습니다   

font-variant-alternates는 글꼴의 기본 글리프(glyphs) 외에도 다양한 대체 글리프(glyphs)를 제공하도록 대체 글리프(glyphs)의 선택을 제어한다.


``` 속성값 : normal | historical-forms | stylistic() |  styleset() | character-variant() |  swash() | ornaments() | annotation() ```   


## font variable를 활용한 문자 애니메이션 예제
```html
    <style>
 @import url('https://fonts.googleapis.com/css2?family=Hepta+Slab:wght@1..900&display=swap');
  span {
    font-family: "Hepta Slab";
    font-size: 5em;
    animation: 3s infinite variation;
  }
   @keyframes variation {
    0% { font-weight: 1;    }
    50% { font-weight: 900;    }
    100% { font-weight: 1;    }
  }
  </style>
    <div></div>
    <script>
let theText = "Hello Everyone~ Nice to see you again"
let box = document.querySelector('div');
let container="";
let myContents="";
for(let i=0; i< theText.length; i++){
    delay = (i*-3) / theText.length
    myContents = `<span style="animation-delay:${delay}s">${theText[i]}</span>`;
    container += myContents;
}
box.innerHTML=container;
    </script>
```

