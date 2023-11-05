##### 🍑  Front_End 과정 1단계 

웹페이지를 만들기 전에 알아야 할 지식은 아래에 있습니다. (전부는 아니지만 대충 이 정도는 알고 있어야 한다고 생각합니다.)

### 가. html 엘리먼트는 시작태그부터 끝태그 사이에 있는 모든 것을 말합니다. 
- 이 엘리먼트(elements)에는 **태그와 속성**으로 이루어져 있고요.  
```
    <tagname> 내용 </tagname>
 ```
- 그리고 이 엘리먼트들은 nested(중첩) 형태로 되어 있곤 합니다.
- html태그는 대소문자를 구분하지 않습니다.  
그러니까 ```<p> 와 <P>```를 같은 것으로 취급합니다  
(참고: https://www.w3schools.com/html/html_elements.asp)  
_그런데 예전에는 태그는 영문소문자를 사용하라고 권고했었습니다_


### 태그소개
#### 1 <!DOCTYPE>
웹문서의 맨 처음에 나오는 문장으로 브라우저에게 해당 문서의 타입을 알려준다 대소문자를 구분하지 않지만 관례에 따라 대문자로 작성한다.   
html5버전으로 해석하라는 의미로 브라우저는 랜더링할때 참조한다. 

#### 2. html 태그
~~html 태그는 대소문자를 구분한다.~~  
웹문서의 최상위요소이며 루트(Root) 요소라고 부른다. ```<html lang="ko"> ,<html lang="en">``` 이라고 작성한다.  

 lang는 해당 문서의 기본적인 언어를 알려주는 문장이다. lang에 지정된 언어로 모든 내용을 기술하겠다는 뜻이 아니라  
 음성 합성 도구를 사용할때 어떤 발음을 사용할지 등에 사용하기 위한 내용으로, 사용할 주된 언어를 명시하는 것이다.   
 #### 3. meta태그
 메타태그에는 <head> </head> 태그안에 들어가면 속성에는 여러가지 요소가 들어갑니다.
 예를들면,
 ```html
  <meta charset="UTF-8">
  <meta name="description" content="Free Web tutorials">
  <meta name="keywords" content="HTML, CSS, JavaScript">
  <meta name="author" content="John Doe">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
```
- charset : html문서의 문자 인코딩을 지정합니다.
- name 속성에는   
  application-name   
  author   
  description   
  generator   
  keywords   
  viewport   
  있습니다.

🔹서치엔진를 위한 키워드를 정의합니다. 
```<meta name="keywords" content="HTML, CSS, JavaScript"> ```   

🔹웹페이지에 대한 설명을 정의합니다.  
```
<meta name="description" content="Free Web tutorials for HTML and CSS">
```   
🔹웹페이지에 대한 작성자를 정의합니다. 
``` <meta name="author" content="이름"> ```   

🔹문서를 새로고침하는 시간을 정의할 수 있습니다. 
``` <meta http-equiv="refresh" content="30"> ```


🔹 웹사이트가 모든 장치에서 잘 보이도록 뷰포트를 설정하는데, width는 장치의 너비를 따르라는 의미이면 두번째부분은 브라우저에 페이지가 처음 로드될때 줌 레벨을 설정하는 것으로 2.0으로 되어 있으면 2개 확대인데 1.0이니까 1배로 보이라는 의미입니다.

``` <meta name="viewport" content="width=device-width, initial-scale=1.0"> ```

이 메타태그는 중요한데 왜냐하면 이것이 웹페이지를 반응형으로 작동하게합니다.




  

