##### 🍑  Front_End 과정 1단계 

## A Guide to Console commands
1. 콘솔에서 개발자모드
   - Mac ( command + ⬆️ + p )
   - Win ( ctrl shift p )
2. console.log( console ) 로 명령어보기


3. <img width="565" alt="스크린샷 2023-12-20 오후 3 07 43" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/569f9c88-bdd4-4953-b4a5-a677591271fd">   
<img width="343" alt="스크린샷 2023-12-20 오후 3 08 32" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/45f3c89f-8952-4c6a-a765-80a17cc04921">   

4. <img width="618" alt="스크린샷 2023-12-20 오후 3 14 37" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/966517c3-d7f3-4fe5-a06f-52148afc46d1">

5. <img width="982" alt="스크린샷 2023-12-20 오후 3 14 48" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/99db7966-5231-4557-af1e-199ae6347c89">


6. <img width="847" alt="스크린샷 2023-12-20 오후 3 18 48" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/f6eea09b-2087-4aaa-8719-1c82c54d129d">

7. <img width="435" alt="스크린샷 2023-12-20 오후 3 53 39" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/768b6e94-82b3-4ef3-8a15-a8602a9e4212">    

8. <img width="435" alt="스크린샷 2023-12-20 오후 3 53 39" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/319a43c5-934c-4bef-9288-a7a58b9b742e">     

9. console.dir() 자바스크립트 표현을 콘솔에 인쇄. DOM 표현을 표시, html 요소를 검사할때 유용할 수 있다. ``` console.dir( document.body) ```
10. Source 탭 :
  - watch : shows curent values for any expressions.   
  - Call stack : shows the nested call chain.    
  - Scope : current variable.    
11. Performance 탭 :
      waterfall : The waterfall chart also referred to as waterfall graph, provides you with a visual representation of how all the assets on your website load. This includes your CSS, Javascript, HTML, images, plugins and third party content.

    


참조) https://css-tricks.com/a-guide-to-console-commands/


## Dev Tools

#### 1. [element 탭]

<img width="418" alt="스크린샷 2023-12-21 오후 2 49 12" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/408e507b-a619-4f52-be80-d6f416ab1884">

#### 2. 접혀있는 내용을 바로 펼쳐보기   
<img width="388" alt="스크린샷 2023-12-21 오후 2 50 44" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/270e52c7-1d27-4ce9-8763-c806bc0d6608">

#### 3. 선택한 내용을 js 코드로 보기   

<img width="412" alt="스크린샷 2023-12-21 오후 2 58 33" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/01082812-496a-41e1-83b5-0730cf1be65c">

붙여넣기 하면 ``` document.querySelector("body > main > article.mobile_only > div") ```   이런식으로 나온다.   


 #### 4. 콘솔에서 직접 DOM 노드에 액세스할 수 있는 다양한 방법
엘리먼트 탭에서 하나의 요소를 클릭한 후 콘솔패널로 이동하여 '$0'엔터 합니다. 

$0예를 들어 DOM 트리에서 현재 선택된 노드에 액세스하는 데 사용할 수 있습니다 . 
$1은 크롬 브라우저, $2, $3등을 사용하여 과거 선택의 역순으로 선택된 노드에 액세스할 수 있도록 하여 한 단계씩 거슬러올라가며 보여줍니다.   

#### 5. 콘솔에서 직접 DOM 노드에 액세스하는 또 다른 방법은 임시 변수이다. 
- Chromium : 우클릭 → “전역변수로 저장” ( Save as global variable , 팝업메뉴 맨 하단)    
- Firefox : 마우스 오른쪽 버튼 클릭 → “콘솔에서 사용”    
- Safari : 마우스 오른쪽 버튼 클릭 → “로그 요소”    

콘솔창에 아래와 같이 출력된다    
```
>temp1
내용출력
```   
#### 6. 스크린샷 찍기
엘리먼트 탭에서 하나의 요소를 선택한 후 **Capture node screenshot**  하며ㄴ 스크린샷이 찍힌 후에 자동 다운로드 됩니다.  열어보면 해당 엘리먼트에 해당하는 브라우저의 스크린이 캡쳐되어 있습니다.   
>html전체 페이지 스크린샷을 찍으려면 노드 에서 동일한 단계를 반복하세요 . 하지만 그렇게 하면 Safari가 요소 배경색의 투명도를 유지한다는 점에 주목할 가치가 있습니다. Chromium과 Firefox는 이를 흰색 배경으로 캡처합니다.

#### 7. 장치   
장치를 클릭해 보라.   
<img width="507" alt="스크린샷 2023-12-21 오후 3 29 08" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/e1c64bc6-f445-4df8-9483-8cc19b54259e">


#### 8.  Layers  
Chrome을 사용하면 대화상자, 알림, 모달과 같은 최상위 레이어 요소를 시각화하고 검사할 수 있습니다. 
요소가 에 추가되면 옆에 배지가 #top-layer표시되며 top-layer, 이를 클릭하면 태그 바로 뒤에 있는 최상위 레이어 컨테이너로 이동합니다 </html>.

<img width="140" alt="스크린샷 2023-12-21 오후 3 45 08" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/04c2f2e1-2e0b-45fb-97af-c2f2006c25cf">


<img width="385" alt="스크린샷 2023-12-21 오후 3 44 21" src="https://github.com/PhoebeYoon/tag_css_js/assets/48478079/a2f3a6d5-21c6-4830-8ee9-2d6010d7d2b3">

