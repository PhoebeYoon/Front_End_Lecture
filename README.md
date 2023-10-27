##### 🍑  Front_End 과정 1단계 


```html
<body>

  <style>
        img {
  --s: 280px; /* image size */
  --b: 5px; /* border thickness */
  --c: #C02942; /* border color */
  --f: 1; /* initial scale */
 width: var(--s);
  aspect-ratio: 1;
  padding-top: calc(var(--s)/5);
  cursor: pointer;
  border-radius: 0 0 999px 999px;

  /*  아바타 */
  --_g: 50% / calc(100% / var(--f)) 100% no-repeat content-box;
  --_o: calc((1 / var(--f) - 1) * var(--s) / 2 - var(--b));
/*  아바타를 둘러싼 동그마미 */

  outline: var(--b) solid var(--c);
  outline-offset: var(--_o);
  background:  radial-gradient(   circle closest-side,
      #ECD078 calc(99% - var(--b)),var(--c) calc(100% - var(--b)) 99%,#0000
     ) var(--_g);

   

  -webkit-mask: linear-gradient(#000 0 0) no-repeat 50% calc(1px - var(--_o)) /
      calc(100% / var(--f) - 2 * var(--b) - 2px) 50%,
    radial-gradient(circle closest-side, #000 99%, #0000) var(--_g);
  
   
   transform: scale(var(--f));
   transition: .5s;
}

img:hover {   --f: 1.35; /* hover scale */ }

body {
  margin: 0;   min-height: 100vh;  display: grid;
  place-content: center;
  background: #E0E4CC;
}
    </style>
<img src="https://assets.codepen.io/1480814/av+1.png" alt="a random avatar picture" >
```
