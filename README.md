##### 🍑  Front_End 과정 1단계 



- mdn https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors


- [attr]  attr이라는 이름의 특성을 가진 요소를 선택합니다.

- [attr=value]
attr이라는 이름의 특성값이 정확히 value인 요소를 선택합니다.

- [attr~=value]
attr이라는 이름의 특성값이 정확히 value인 요소를 선택합니다. attr 특성은 공백으로 구분한 여러 개의 값을 가지고 있을 수 있습니다.

- [attr|=value]
attr이라는 특성값을 가지고 있으며, 그 특성값이 정확히 value이거나 value로 시작하면서 -(U+002D) 문자가 곧바로 뒤에 따라 붙으면 이 요소를 선택합니다. 보통 언어 서브코드(en-US, ko-KR 등)가 일치하는지 확인할 때 사용합니다.

- [attr^=value]
attr이라는 특성값을 가지고 있으며, 접두사로 value가 값에 포함되어 있으면 이 요소를 선택합니다.

- [attr$=value]
attr이라는 특성값을 가지고 있으며, 접미사로 value가 값에 포함되어 있으면 이 요소를 선택합니다.

- [attr*=value]
attr이라는 특성값을 가지고 있으며, 값 안에 value라는 문자열이 적어도 하나 이상 존재한다면 이 요소를 선택합니다.

- [attr operator value i]
괄호를 닫기 전에 i 혹은 I를 붙여주면 값의 대소문자를 구분하지 않습니다. (ASCII 범위 내에 존재하는 문자에 한해서 적용됩니다)


```html
<style>
a {
  color: blue;
}

/* Internal links, beginning with "#" */
a[href^="#"] {
  background-color: gold;
}

/* Links with "example" anywhere in the URL */
a[href*="example"] {
  background-color: silver;
}

/* Links with "insensitive" anywhere in the URL,
   regardless of capitalization */
a[href*="insensitive" i] {
  color: cyan;
}

/* Links with "cAsE" anywhere in the URL,
with matching capitalization */
a[href*="cAsE" s] {
  color: pink;
}

/* Links that end in ".org" */
a[href$=".org"] {
  color: red;
}
</style>

<ul>
  <li><a href="#internal">Internal link</a></li>
  <li><a href="http://example.com">Example link</a></li>
  <li><a href="#InSensitive">Insensitive internal link</a></li>
  <li><a href="http://example.org">Example org link</a></li>
</ul>
```
그외,
```html
/* All divs with a `lang` attribute are bold. */
div[lang] {
  font-weight: bold;
}

/* All divs in US English are blue. */
div[lang~="en-us"] {
  color: blue;
}

/* All divs in Portuguese are green. */
div[lang="pt"] {
  color: green;
}

/* All divs in Chinese are red, whether
   simplified (zh-CN) or traditional (zh-TW). */
div[lang|="zh"] {
  color: red;
}

/* All divs with a Traditional Chinese
   `data-lang` are purple. */
/* Note: You could also use hyphenated attributes
   without double quotes */
div[data-lang="zh-TW"] {
  color: purple;
}

<div lang="en-us en-gb en-au en-nz">Hello World!</div>
<div lang="pt">Olá Mundo!</div>
<div lang="zh-CN">世界您好！</div>
<div lang="zh-TW">世界您好！</div>
<div data-lang="zh-TW">世界您好！</div>



```



