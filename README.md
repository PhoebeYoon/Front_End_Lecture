##### 🍑  Front_End 과정 1단계 

```html
 <style>
    p { color: dodgerblue}
  /* strong { color: initial} */
</style>

<p>Lorem ipsum <strong>dolor</strong> sit Aut, atque.</p>
```

strong태그가 상속한 것을 기본값으로 되돌리려면 initial 속성을 사용하면 된다.    
그런데 만약 p태그에 border 속성을 주면 strong 태그도 그 속성을 상속할까?    
border 속성은 상속되지 않는다.   
만약 상속받게 하려면 아래와 같이 해준다. 

```css
<style>
      p { color: dodgerblue; border: 1px solid;}
      /* strong { color: initial} */
      strong { border: inherit}
</style>
```
그럼 어떤 속성은 상속되고 어떤 속성은 그렇지 않은가?  여기에 리스트가 존재하는데  그렇다고 외울필요는 없다.   
보통 글자 폰트, 색상,크기, 정렬 이런 속성은 상속된다
