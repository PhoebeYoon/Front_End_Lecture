##### 🍑  Front_End 과정 1단계 


## text-wrap

text-wrap CSS 속성은 요소 내부의 텍스트가 랩되는 방식을 제어합니다. 다른 값은 다음을 제공합니다:
1. wrap
2. nowrap
3. balance

>Note: The white-space-collapse and text-wrap properties can be declared together using the white-space shorthand property.

```html
<style>
  h1 { text-wrap: balance;} // text-wrap: nowrap, wrap 으로 바꿔본다
 브라우저의 너비를 좁게 한 후 오른쪽끝에서 일어나는 줄바꿈을 확인해 본다 
</style>
 <h1>Heading can be long, wrap, nowrap, balance</h1>
```
