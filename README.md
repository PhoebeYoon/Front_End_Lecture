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

## font-variant-alternates:
``` 속성값 : normal | historical-forms | stylistic() |  styleset() | character-variant() |  swash() | ornaments() | annotation() ```   
