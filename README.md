##### 🍑  Front_End 과정 1단계 


참고) https://css-irl.info/logical-border-radius/

``` border-radius: 2rem 8rem 8rem 9rem / 3rem 11rem 6rem 5rem; ``` 
                    1    2    3    4   /   5    6     7   8   


       1              2
    5                    6
    8                    7
       4              3

```html
 <style>
* { box-sizing: border-box;}
body {
	font-family: 'Helvetica', sans-serif;
	margin: 0;
	padding: 1rem;
	display: flex;
	align-items: center;
	justify-content: center;
	min-height: 100vh;
	direction: ltr;
}

.rtl .grid { direction: rtl;}
header { margin-block-end: 2rem;}
button {
	border: none;
	background: lightblue;
	padding: 0.5rem 1rem;
	border-radius: 0.5rem;
	box-shadow: 0.1rem 0.1rem 0.5rem rgb(0 0 0 / 0.05);
}

button[aria-pressed="true"] {background: cornflowerblue; }

.grid {
	display: grid;
	grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
	gap: 1rem;
}

.wrapper { max-inline-size: 60rem; inline-size: 100%; }
.grid { counter-reset: grid; }
.grid > div {
	background: pink;
	aspect-ratio: 1;
	display: flex;
	justify-content: center;
	align-items: center;
}

.grid > div:nth-child(even) { background: turquoise; }

.grid > div::after {
	counter-increment: grid;
	content: counter(grid);
}

.grid > div:first-child {
/* 	border-top-left-radius: 50% 75%; */
	border-start-start-radius: 50% 75%;
}

.grid > div:nth-child(2) {
/* 	border-top-right-radius: 50% 75%; */
	border-start-end-radius: 50% 75%;
}

.grid > div:nth-child(3) {
/* 	border-bottom-right-radius: 50% 75%; */
	border-end-end-radius: 50% 75%;
}

.grid > div:nth-child(4) {
/* 	border-bottom-left-radius: 50% 75%; */
	border-end-start-radius: 50% 75%;
}

.grid > div:nth-child(5) {
	border-radius: 10% 20% 30% 75%;
}

.grid > div:nth-child(6) {
	background: aquamarine;
	border-radius: 2rem 8rem 8rem 9rem / 3rem 11rem 6rem 5rem;
}

.grid > div:nth-child(7) {
	background: lavender;
	border-radius: 5rem 1rem / 50%;
/* 	border-top-left-radius: 5rem 50%;
	border-top-right-radius: 2rem 50%;
	border-bottom-right-radius: 5rem 50%;
	border-bottom-left-radius: 2rem 50%; */
}

.grid > div:nth-child(8) {
	background: lavender;
	border-top-right-radius: 100% 80%;
	border-bottom-right-radius: 100% 80%;
	border-bottom-left-radius: 50% 50%;
}
    </style>
   <div class="wrapper">
	<header>
		<button data-switch role="switch" aria-pressed="false">Switch direction</button>
		<span data-span>ltr</span>
	</header>

	<div class="grid">
		<div></div>
		<div></div>
		<div></div>
		<div></div>
	</div>
</div>
      <script>
 const btn = document.querySelector('[data-switch]')
const text = document.querySelector('[data-span]')

btn.addEventListener('click', (e) => {
  const isPressed = e.target.getAttribute('aria-pressed') === 'true'
  
  if (isPressed) {
    e.target.setAttribute('aria-pressed', 'false')
    text.innerText = 'ltr'
    document.body.classList.remove('rtl')
  } else {
    e.target.setAttribute('aria-pressed', 'true')
    text.innerText = 'rtl'
    document.body.classList.add('rtl')
  }
})
      </script>

```

