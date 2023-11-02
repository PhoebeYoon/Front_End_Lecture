##### 🍑  Front_End 과정 1단계 

일단 아래의 예를 실행해 보고 차이점을 알아봅시다. 


## input:focus / :focus-within / :focus-visible 에 대해 알아본다

input태그에 들어가는 :focus 는 이제까지 사용해 왔던 것인데 이것에 더하여 :widthin , :focus-visible라는 것이 생겼다. 
focus 라는 상태는 모든 엘리먼트에 적용되는 것은 아니다. input, button, form, link, a 태그와 같은 경우에 focus 상태를 가진다.  


```html
<style>
.form__input:focus-visible {
  outline: 3px dashed gold;
  outline-offset: .25rem;
}

/* .form:focus-within {
  outline: 3px solid limegreen;
  outline-offset: 1rem;
} */

/* .form__group:focus-within {
  outline: 3px solid white;
  outline-offset: .25rem;
} */
</style>
<div class="steam-signup-form">
    <div class="front">
       <span class="logo">😻</span> 
    <h1 class="title">Create your account</h1>
    <p>The ultimate entertainment platform</p>
    <p>Play, connect, create and more.</p>
    <p><strong>It's free to join and easy to use.</strong></p>
    
    <form class="form" action="">
      <div class="form__group">
        <label class="form__label" for="email">Your Email <span class="form__tooltip" data-tooltip="Please enter your email address">?</span></label>
        <input class="form__input" type="email" id="email" name="email">
      </div>
      <div class="form__group">
        <label class="form__label" for="password">Password <span class="form__tooltip" data-tooltip="Minimum 12 characters, at least one capital and one number">?</span></label>

        <input class="form__input" type="password" id="password" name="password" placeholder="****">

      </div>
        <div class="form__group">
        <label class="form__label" for="password-reenter">Re-enter password</label>
      <input class="form__input" type="password" id="password-reenter" name="password-reenter">
    </div>
        
      <p class="fineprint flex-center">
        <input class="form__checkbox" type="checkbox" id="agreement" name="agreement">
        <label for="agreement">I am 13 years of age or older AND agree to the <a href="#">terms and serivces</a>.</label>
      </p>
      <p>
        <img class="recaptcha" src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/308367/recaptcha-dark.png" alt="">
      </p>
      
      <button class="button">Sign up now</button>
      <a href="#" class="fineprint">I already have an account</a>      
    </form>
    
  </div>  
</div>

``` 

## :focus and :focus-visible 차이 

보통 focus를 갖는 이벤트로는 클릭과 키보드 탭키를 사용해서이다. 아래의 경우에는 마우스클릭과 탭키 사용에 있어서 :focus 와 : focus-visible의 차이를 보여준다. 

```html
    <style>
input, button { margin: 10px; }
.focus-only:focus { outline: 2px solid black; }
.focus-visible-only:focus-visible { outline: 4px dashed darkorange;}
    </style>
<input type="text" value="Default styles" /><br />
<button>Default styles</button><br />
<input class="focus-only" type="text" value=":focus" /><br />
<button class="focus-only">:focus</button><br />
<input class="focus-visible-only" type="text" value=":focus-visible" /><br />
<button class="focus-visible-only">:focus-visible</button>
```
focus-only는 마우스이든 탭이든 모두 동일하게 작동하지만 
focus-visible-only클래스는 마우스로 focus 할때와 탭으로 focus할때 다르다. 마우스로 버튼을 클릭하면 해당 스타일이 적용되지 않지만 키보드 탭으로 하게 되면 동일하게 작동한다.  
그런데 왜 이런게 나왔을까?  기존의 사용에서 어떤 브라우저에서는 포커스링 이라 불리는 경계선이 나타나기도 했다. 그래서 일부러 outline:none 뭐 이런것을 주어서 이 포커스링을 보이지 않게 처리했다. 이 포커스링이 나타나는 이유는 주로 마우스 대신 탭키를 이용하여 선택할때 주로 나타났다.   
이것을 마우스에는 반응하지 않고, 탭키를 클릭했을때만 반응하도록 하면 어떨까? 해서 나온 아이디어가 아닐까 싶다 (내 생각 :) 
마우스로 버튼을 클릭하려고 했는데 의도하지 않는 포커스링이 나타나면 좀 이상하니까... 

```html
<style>
.wrapper {
  background: black;  text-align: center;
  width: 360px;  height: 100px;
  padding: 40px;  box-sizing: border-box;
  color: blanchedalmond;
}
.image-nav-button {
  color: blanchedalmond;  text-decoration: none;
  font-size: 20px;  line-height: 1em;
}
.next {  float: right;}
.prev {  float: left;}
.image-nav-button:focus {  outline: none;
  /* Try uncommenting below, then clicking the buttons */
  /* outline: 3px solid red; */
}
.image-nav-button:focus-visible {
  outline: 3px solid blanchedalmond;
}
    </style>

<div class="wrapper">
  <a href="#" tabindex="1" class="image-nav-button prev">&larr; Prev Image</a>
  <a href="#"  tabindex="2" class="image-nav-button next">Next Image &rarr;</a>
</div>

```

