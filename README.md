##### 🍑  Front_End 과정 1단계 

## color-schema

The color-scheme CSS property allows an element to indicate which color schemes it can comfortably be rendered in.

Common choices for operating system color schemes are "light" and "dark", or "day mode" and "night mode". When a user selects one of these color schemes, the operating system makes adjustments to the user interface. This includes form controls, scrollbars, and the used values of CSS system colors.
운영 체제 색상 체계에 대한 일반적인 선택은 "light" 및 "dark" 또는 "day mode" 및 "night mode"입니다. 사용자가 이러한 색상 체계 중 하나를 선택하면 운영 체제는 사용자 인터페이스를 조정합니다. 여기에는 폼 컨트롤, 스크롤 바 및 CSS 시스템 색상의 사용된 값이 포함됩니다.


## 윈도우 > 설정 (개인설정) > 색 > "기본 앱 모드 선택"
여기에서 밝게 / 어둡게를 바꾸면 색상이 변경된다

```html
body { background:beige;}

@media (prefers-color-scheme: dark) {
  body { background: navy }
}

```


## localStoage를 이용하여 클릭 및 페이지로드에도 반응하도록 제작

```html
    <style>
        @import url("https://fonts.googleapis.com/css?family=Assistant:400,700|Playfair+Display:900");

*,
*::before,
*::after {
  box-sizing: border-box;
}

:root {
  --clr-light: #fdffc4;
  --clr-dark: #00332a;
  --clr-primary: #dbffa2;
  --clr-secondary: #c3fcf2;
  --clr-accent: #ff7750;

  --foreground: var(--clr-dark);
  --background: var(--clr-light);

  --ff-title: "Playfair Display", serif;
  --ff-body: "Assistant", sans-serif;
}

.darkmode {
  --clr-light: #fdffc4;
  --clr-dark: #00332a;
  --clr-primary: #202302;
  --clr-secondary: #00100d;
  --clr-accent: #ff7750;

  --foreground: var(--clr-light);
  --background: var(--clr-dark);
}


body {
  background: var(--background);
  color: var(--foreground);
  font-family: var(--ff-body);
  font-size: 18px;
  line-height: 1.6;
}

h1 {
  font-size: calc(3rem + 7vw);
  font-family: var(--ff-title);
  margin: 0 0 0.25em;
  line-height: 1;
}

.subtitle {
  max-width: 600px;
}

.btn-group {
  margin: 2em 0;
  display: relative;
}

.btn {
  padding: 1em 2em;
  text-decoration: none;
  text-transform: uppercase;
  border-radius: 5px;
  position: relative;
  display: inline-block;
  line-height: 1;
}

.btn + .btn {
  margin-left: 1em;
}

.btn-secondary {
  background: var(--foreground);
  color: var(--background);
  // border: currentColor solid 2px;
}

.btn-accent {
  background: var(--clr-accent);
  color: var(--foreground);
}

.btn::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border: var(--foreground) 2px solid;
  left: -4px;
  top: 4px;
  border-radius: inherit;
  z-index: -1;
}

.intro {
  height: 80vh;
  padding: 10em 0;
  display: grid;
  grid-template-columns: minmax(2em, 1fr) minmax(80vw, 860px) minmax(2em, 1fr);
  background: linear-gradient(120deg, var(--clr-primary), var(--clr-secondary));
  align-content: center;
}

.intro > * {
  grid-column: 2 / 3;
}

.dark-mode-toggle {
  position: absolute;
  z-index: 100;
  top: 1em;
  right: 1em;
  color: var(--foreground);
  border: 2px solid currentColor;
  padding: 4px;
  background: transparent;
  cursor: pointer;
  border-radius: 5px;
  width: 30px;
  height: 30px;
}

.click-here {
  width: 100px;
  right: 1.5em;
  position: absolute;
  top: 3em;
}
    </style>
<section class="intro">      
        <h1>Amazing Product</h1>
        <p class="subtitle">Lorem ipsum dolor sit amet consectetur adipisicing elit.
 Voluptates rem molestias ipsum nulla libero optio.</p>  
        <div class="btn-group"> 
          <a href="#" class="btn btn-accent">Purchase</a>
          <a href="#" class="btn btn-secondary">More info</a>
        </div>
      </section>
      <button id="dark-mode-toggle" class="dark-mode-toggle">
        &#128280;
      </button>
      <div class="click-here">
       click here&#x2197;
      </div>

<script>
let darkMode = localStorage.getItem('darkMode')
const darkModeToggle = document.querySelector('#dark-mode-toggle');

const enableDarkMode =()=>{
    document.body.classList.add('darkmode');
    localStorage.setItem('darkMode','enabled')
}

const disableDarkMode=()=>{
    document.body.classList.remove('darkmode');
    localStorage.setItem('darkMode', null)
}
if (darkMode ==='enabled') {
    enableDarkMode();
}
darkModeToggle.addEventListener('click', ()=>{
    darkMode = localStorage.getItem('darkMode')
    if(darkMode !== 'enabled'){
        enableDarkMode()
    }else {
    disableDarkMode();}
})
</script>
```

페이지를 로드하게되면 light 모드가 적용된다. 클릭하여 dark 모드로 바꾼후에도 페이지를 리로드하게되면 light 모드부터 다시 시작된다. 그래서 localStorage에 내용을 저장하고 페이지가 다시 로드할때 localStorage에서 해당 내용을 가져오므로 클릭 및 로드에서 설정한 내용대로 적용되도록 한다. 




