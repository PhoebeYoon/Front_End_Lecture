##### 🍑  Front_End 과정 1단계 

## aria-hidden 속성

aria-hidden 상태는 요소가 접근성 API에 노출되는지 여부를 나타냅니다. 일반적인 브라우저에서 내용을 보여주는 것이 아니라 스크린리더기와 같은 장비를 사용하는 경우 정보의 내용을 스크린리더가 사용하지 못하도록 할 수 있습니다. 

콘텐츠를 숨기는 방법으로는 CSS활용해 display : none, visibility:hidden 을 활용할 수 있습니다.  스크린 리더 사용자는 시각적 콘텐츠를 음성으로 변환하여 이해합니다 그러나 너무나 많은 정보는 오히려 이해를 어렵게 할 수 있습니다. aria-hidden을 사용하여 불필요한 정보를 제거함으로써 사용자의 이해를 돕습니다.
또한 이를 이용해서 숨겨진 콘텐츠를 초기에는 보이지 않게 했다가 스크린리더 사용자에게 제공할 수도 있습니다. 또한 aria-hidden는 검색엔진에 노출되지 않으므로 무의미한 콘텐츠를 숨길 수도 있습니다.


```   <div class="noshow" aria-hidden="true">hello</div>  ```
구글의 확장프로그램 중 'Screen Reader' 를 설치하고 페이지를 열어보면 aria-hidden=true 일때는 내용을 읽지 않습니다. false 로 바꾸면 해당 내용을 읽습니다. 

기존에 내용을 안 보이게 할때 보통은,
display: none, opacity:0; visibiliy:hidden  처리할 수 있지만 aria-hidden를 이용할 수도 있습니다 

### 내용을 감추는 여러가지 방법

CSS display: none   
CSS visibility: hidden   
Visually Hidden: Off-Screen ( 예,  left: -100vw; )   

출처:https://www.scottohara.me/blog/2017/04/14/inclusively-hidden.html
 
