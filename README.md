##### 🍑  Front_End 과정 1단계 


## svh는 모바일에서 사용하도록 

우리가 웹페이지의 100vh를 지정하곤 한다. 그런데 이것을 모바일에서 사용하게 되면 모바일 상단에 띄어져 있는 주소창때문에 
진정한 100vh가 아닌것처럼 나온다.   

### 1.  dvh (Dynamic Viewport Height)
   dvh는 주소 표시줄이 스크롤을 통해 축소가 되건 노출이 되고 있건 상관 없이 현재 보여지는 뷰포트 높이를 동적으로 가져온다
그러므로 100dvh는 주소표시줄의 유무에 따라 값이 달라진다.

### 2. svh (Short Viewport Height)
   svh는 사용자 화면 기준으로 가장 짧은 뷰포트 값을 가져온다.  주소 표시줄이 없어져도 기존 주소표시줄의 높이 값을 뺀 나머지 값을 가져온다.

### 3. lvh (Large Viewport Height)
   lvh는 svh와는 반대로 사용자 화면 기준으로 가장 긴 뷰표트 값을 가져온다. 주소 표시줄이 있더라도 주소 표시줄이 없을 때의 총 화면의 길이를 가져온다.


```css
header{
   min-height:100vh;
   min-height:100svh;
}
```

실습내용 출처 : https://www.youtube.com/watch?v=ru3U8MHbFFI&t=297s    
