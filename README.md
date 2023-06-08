# Front_End_Lecture


1. vs code 기본사용법
2. box model ( padding, margin, border , box-size:border-box)
3. 앵커태그 (:link, :hover ,:active ,:visited )
4. display : none, display:visible
5. px, em, rem 단위
6. @media screen () {}  모바일버전 : min-width: 작은사이즈부터 큰 사이트 | 웹사이트 : max-width: 큰사이즈부터 작은 사이즈 순으로 
7. position: relative, absolute
8. 
``` css
@media (orientation : landscape) {

}

@media (orientation : portrait) {

}

```
8. 가로세로비 (Aspect ratio) - 영상의 가로세로비는 화면비라고도 불리며, 가로의 길이를 세로의 길이로 나눈 값으로 표시한다. 예를 들어, 기존 텔레비전 화면의 가로세로비는 4:3 혹은 1.33:1 이었다. 고선명 텔레비전과 유럽의 디지털 텔레비전은 약 1.78:1의 16:9의 가로세로비를 사용한다.   
aspect-ratio: 1 / 1;
aspect-ratio: 16 / 9;
aspect-ratio: 0.5;

```css
@media (min-aspect-ratio: 1/1) { // 가로 세로의 비율이 1대1
.box { background:red }
}


@media (min-aspect-ratio: 16/9) {  // 가로 세로의 비율에서 가로가 길다
.box { background:red }
}

또한 
@media (width >=300px) {    }
@media (width =300px) {    }
@media (width <=300px) {    }
@media (100px <= width <=300px) {     }

```    

참조사이트 : https://caniuse.com/?search=range%20media    

https://developer.mozilla.org/en-US/docs/Web/CSS/background    
https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility     
https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter    
