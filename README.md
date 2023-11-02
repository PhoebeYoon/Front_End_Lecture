##### 🍑  Front_End 과정 1단계 


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

