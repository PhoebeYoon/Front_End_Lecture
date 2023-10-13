##### 🍑  Front_End 과정 1단계 
## contenteditable
input, textarea와 같은 입력태그와는 다르게 다른 태그, 예를들어 <div>같은 태그에 문자열 편집이 가능하게 합니다.   

``` html
<style>
blockquote {   background: #eee;
  border-radius: 5px;  margin: 16px 0; }

blockquote p {  padding: 15px;}
cite {  margin: 16px 32px;  font-weight: bold;}

blockquote p::before {  content: '\201C';}
blockquote p::after {  content: '\201D';}
[contenteditable='true'] {  caret-color: red;}
</style>

<blockquote contenteditable="true">
  <p>Edit this content to add your own quote</p>
</blockquote>
<cite contenteditable="true">-- Write your own name here</cite>

```
