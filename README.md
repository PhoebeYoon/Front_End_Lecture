##### 🍑  Front_End 과정 1단계 


#### 🍑 실행을 위한 사전 준비과정 (윈도우)
1. 제이쿼리 설치 - https://cdnjs.com/libraries/jquery 에서 코드복사
2. 크롬( ~ has been blocked by CORS policy 하면서 실행 안될때  )
  -  크롬아이콘의 속성
  -  바로가기 탭 : 대상 :  "C:\Program Files\Google\Chrome\Application\chrome.exe" --disable-web-security --disable-gpu --user-data-dir=~/tmp
  뒷부분 추가
  - 크롬의 "관리자 권한으로 실행"
  - 크롬 주소창에 해당 파일 입력

### Ajax으로 하는 실습 
기존 p태그의 내용을 data.txt안에 있는 p태그의 내용으로 바꾼다

```html
 <title>Document</title>
  <script>
    $(document).ready(function(){
      $("#btn").click(function(){
        $("#test").load("./data.txt", { 
          Name: "Daniel" , 
          Lastname : "GilDong" 
        }, function(){
         alert("Hi there!")
    
        })
      })
  })
  </script>
<div id="test">
    <p>this is the first content</p>
  </div>
  <button id="btn">Click to change</button>
  <div id="demo">
  </div>

```

