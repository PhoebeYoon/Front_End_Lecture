##### 🍑  Front_End 과정 1단계 

## localStorage
localStorage 개체는 만료 날짜 없이 데이터를 저장합니다. 브라우저를 닫을 때 데이터는 삭제되지 않으며 다음 날, 주 또는 연도에 사용할 수 있습니다.



```html
<!DOCTYPE html>
<html>
<body>

<div id="result"></div>

<script>
// Check browser support
if (typeof(Storage) !== "undefined") {
  // Store
  localStorage.setItem("lastname", "Smith");
  // Retrieve
  document.getElementById("result").innerHTML = localStorage.getItem("lastname");
} else {
  document.getElementById("result").innerHTML = "Sorry, your browser does not support Web Storage...";
}
</script>

</body>
</html>

```   
## sessionStorage   
sessionStorage 개체는 하나의 세션에 대한 데이터만 저장한다는 점을 제외하고 localStorage 개체와 동일합니다. 사용자가 특정 브라우저 탭을 닫으면 데이터가 삭제됩니다.   

```html
<!DOCTYPE html>
<html>
<head>
<script>
function clickCounter() {
  if (typeof(Storage) !== "undefined") {
    if (sessionStorage.clickcount) {
      sessionStorage.clickcount = Number(sessionStorage.clickcount)+1;
    } else {
      sessionStorage.clickcount = 1;
    }
    document.getElementById("result").innerHTML = "You have clicked the button " + sessionStorage.clickcount + " time(s) in this session.";
  } else {
    document.getElementById("result").innerHTML = "Sorry, your browser does not support web storage...";
  }
}
</script>
</head>
<body>

<p><button onclick="clickCounter()" type="button">Click me!</button></p>
<div id="result"></div>
<p>Click the button to see the counter increase.</p>
<p>만약, 브라우저를 닫은 후 다시 실행하면 카운터는 초기화됩니다 </p>

</body>
</html>

```




