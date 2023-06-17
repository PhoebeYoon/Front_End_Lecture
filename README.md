##### 🍑  Front_End 과정 1단계 


## Input 관련이벤트 

focus : 요소가 포커스가 되고 커서가 발생하여 입력이 가능해졌을 때 발생하는 이벤트입니다. 이후 진행되는 인풋 관련 이벤트들이 발생하고 감지될 수 있는 시작점이 됩니다.
blur : 요소의 포커스가 해제되었을 때 발생하는 이벤트입니다.

change : focus가 발생하기 전의 원래 입력값과 비교하여 변화가 일어났을 경우 blur 이벤트 이후에 발생하는 이벤트입니다.

input : value 속성의 값이 바뀔 때마다 발생하는 이벤트입니다. 일반적으로 keyPress 직후에 value 속성이 바뀌면서 input 이벤트가 발생합니다. input 이벤트 객체의 data 프로퍼티는 value 속성에 가장 최근 추가된 한 글자를 가지고 있습니다.(영어의 경우 알파벳 한 글자, 한국어의 경우 초성/중성/종성으로 이루어진 한 글자)

keyDown : 키가 눌렸을 때 발생합니다. input 이벤트 전에 발생됩니다.

keyPress : 키가 눌렸을 때 발생하며, keyDown 이벤트 이후에 발생합니다. 한글 입력이나 기능키 입력시에는 발생하지 않습니다. MDN에서 찾아보면 deprecated 되었다고 나오니, input 이벤트 전에 입력을 제어하고 싶다면 keyDown 이벤트를 사용하는게 바람직해 보입니다. keyDown과 여러모로 비슷한 특성을 가지지만 특정 키에는 발생하지 않는 등의 예기치 않은 동작으로 혼란을 줄 수 있는 이벤트가 아닐까 생각합니다.

keyUp : input 이벤트 발생 후 value가 업데이트 된 이후에 키보드에서 손을 떼면 발생하는 이벤트입니다. 당연하게도 키를 꾹 눌러서 입력을 반복하거나 할때는 발생하지 않습니다.

```

<template>
  <div id="app">
    <input
      v-model="inputValue"
      @focus="onFocus"
      @blur="onBlur"
      @keydown="onKeyDown"
      @keypress="onKeyPress"
      @keyup="onKeyUp"
      @input="onInput"
      @change="onChange"
    />
  </div>
</template>
​
<script>
export default {
  name: "App",
  data: () => ({
    inputValue: "",
  }),
  methods: {
    onFocus(e) {
      console.log("focus event occur!!", `current input value: ${e.target.value}`);
    },
    onBlur(e) {
      console.log("blur event occur!!", `current input value: ${e.target.value}`);
    },
    onKeyPress(e) {
      console.log("keyPress event occur!!", `input key: ${e.key}/current input value: ${e.target.value}`);
    },
    onKeyDown(e) {
      console.log("keyDown event occur!!", `input key: ${e.key}/current input value: ${e.target.value}`);
    },
    onBeforeInput(e) {
      console.log("input event occur!!", `input key: ${e.data}/current input value: ${e.target.value}`);
    },
    onInput(e) {
      console.log("input event occur!!", `input data: ${e.data}/current input value: ${e.target.value}`);
    },
    onKeyUp(e) {
      console.log("keyUp event occur!!", `input key: ${e.key}/current input value: ${e.target.value}`);
    },
    onChange(e) {
      console.log("change event occur!!", `current input value: ${e.target.value}`);
    },
    onPaste(e) {
      console.log("paste event occur!!", `current input value: ${e.target.value}`);
    },
  },      
};
</script>

```

2. keyDown 이벤트 핸들러에서 input이벤트 발생 전 입력 평가하기
keyDown 이벤트 객체에서 key 프로퍼티를 통해 입력한 key에 접근할 수 있습니다. keyDown 이벤트는 아직 input이벤트가 발생하여 input 요소의 value 값이 바뀌기 전이므로, 입력을 평가해 value 값 반영 여부를 결정하기에 좋은 이벤트입니다. keyDown 이벤트 핸들러 함수를 Vue 인스턴스 method 프로퍼티에 작성해주고, input 요소에 이벤트를 바인딩해줍니


```
<template>
​
  <div id="app">
    <input
      @keydown="onKeyDown"
    />
  </div>
</template>
​
<script>
export default {
  name: "NumericInput",,
  data: () => ({
    inputValue: "",
    allowKey: ['0','1','2','3','4','5','6','7','8','9', 'Backspace']
  }),
  methods: {
    onKeyDown(e) {
      if(!this.allowKey.includes(e.key)) {
        e.preventDefault()
      }
    },
  },
};
</script>
```



paste 이벤트 핸들러에서 input 이벤트 취소하기
그런데 입력은 키보드로만 하는것이 아닙니다. 마우스 오른쪽 버튼을 눌러서 클립보드에 복사한 문자열을 붙여넣기 할수도 있겠죠. 이런 경우에 붙여넣기를 감지하는 paste 이벤트를 활용해 입력을 평가하고 결과에 따라 input 이벤트를 취소해야 합니다. 다음과 같이 paste 이벤트 핸들러를 추가해주고, input 요소에 이벤트를 바인딩합니다.



focus => keyDown => (keyPress) => input => keyUp => blur => change
```
<template>
  <div id="app">
    <input
      @keydown="onKeyDown"
      @paste="onPaste"
    />
  </div>
</template>
​
<script>
export default {
  name: "NumericInput",,
  data: () => ({
    inputValue: "",
    allowKey: ['0','1','2','3','4','5','6','7','8','9', 'Backspace']
  }),
  methods: {
    onKeyDown(e) {
      if(!this.allowKey.includes(e.key)) {
        e.preventDefault()
      }
    },
    onPaste(e) {
      const pasteData = e.clipboardData.getData('text')
      for (const data of pasteData.split('')) {
         if(!this.allowKey.includes(data)) {
          e.preventDefault()
          break
        }
      }
    },
  },
};
</script>

```

4. input 요소의 value 속성값을 Vue 인스턴스로 옮기기    
여기까지 진행했다면 시각적으로는 완벽합니다. 인풋 요소는 숫자가 아닌 입력을 하나도 허용하지 않습니다. 하지만 input 요소의 입력을 Vue 인스턴스의 변수로 옮겨야 입력 데이터를 가지고 여러가지 처리를 할 수 있습니다. value 속성값을 자바스크립트 변수로 옮기는 방법은 몇 가지가 있지만 이번 포스팅에서는 input 이벤트 핸들러를 추가하여 data() 속성의 Vue 인스턴스 변수로 value 속성값을 옮겨보도록 하겠습니다. input 이벤트 핸들러를 작성해줍니다.


```
<template>
​
  <div id="app">
    <input
      @keydown="onKeyDown"
      @paste="onPaste"
      @input="onInput"
    />
  </div>
</template>
​
<script>
export default {
  name: "NumericInput",
  data: () => ({
    inputValue: "",
    allowKey: ['0','1','2','3','4','5','6','7','8','9', 'Backspace']
  }),
  methods: {
    onKeyDown(e) {
      if(!this.allowKey.includes(e.key)) {
        e.preventDefault()
      }
    },
    onPaste(e) {
      const pasteData = e.clipboardData.getData('text')
      for (const data of pasteData.split('')) {
         if(!this.allowKey.includes(data)) {
          e.preventDefault()
          break
        }
      }
    },
    onInput(e) {
      this.inputValue = e.target.value
    },
  },
};
</script>


```



출처 : https://maxkim-j.github.io/posts/keyboard-input/











