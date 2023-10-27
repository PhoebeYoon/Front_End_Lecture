##### 🍑  Front_End 과정 1단계 

## SpeechRecognition 
Web Speech API의 Speech Recognition 음성인식 서비스를 위한 인터페이스이다. 이것은 또한  인식서비스로부터 보내온 SpeechRecognition이벤트를 다룬다   

### 인스턴스 속성
- SpeechRecognition.grammars : 이해할 문법을 나타내는 개체 컬렉션을 반환하고 설정
- SpeechRecognition.lang : 언어설정. 특별히 지정되지 않는다면 HTML의 lang 속성의 값을 반영한다.
- SpeechRecognition.continuous : 각 인식에 대한 연속결과가 반환되는지, 단일결과가 반환되는지 , 기본값은 단일(false)이다.
- SpeechRecognition.interimResults : 중간결과를 반환해야 하는지 (true) 반환하지 말아야 하는지(false)를 제어한다.
           (중간결과는 최종결과가 아니므로 SpeechRecognitionResult.isFinal 의 속성은 false이다 )
- SpeechRecognition.maxAlternatives : 결과당 제공되는 최대수로 기본값은 1이다

### 인스턴스 메소드
- SpeechRecognition.abort()
- SpeechRecognition.start()
- SpeechRecognition.stop()
  
### 인스턴스 이벤트
addEventListener()이벤트를 할당하여 수신한다.
- audiostart : user agent 가 오디오를 시작하면 작동한다
- audioend
- end : 음성 인식 서비스가 연결이 끊어졌을 때 발생합니다
- error
- nomatch
- result : 음성 인식 서비스가 결과를 반환할 때 발생 - 단어나 구가 긍정적으로 인식되어 앱으로 다시 전달되었으며, onresult 속성을 통해서도 사용 가능합니다.
- soundstart
- soundend
- speechstart : 음성인식서비스에서 음성으로 인식한 소리가 감지되면 발화되며, onspeech start 속성을 통해서도 사용할 수 있습니다
- speechend
- start : 음성 인식 서비스가 현재 음성 인식과 연관된 문법을 인식하기 위해 수신 오디오를 듣기 시작할 때 발생하며, onstart 속성을 통해서도 사용할 수 있습니다.

```html
  <style>
    html {      font-size: 10px;   }
    body {      background: #ffc600;      font-family: 'helvetica neue';
      font-weight: 200;      font-size: 20px;    }
    .words {      max-width: 500px;      margin: 50px auto;
      background: white;      border-radius: 5px;
      box-shadow: 10px 10px 0 rgba(0,0,0,0.1);
      padding: 1rem 2rem 1rem 5rem;
      background: -webkit-gradient(linear, 0 0, 0 100%, from(#d9eaf3), color-stop(4%, #fff)) 0 4px;
      background-size: 100% 3rem;      position: relative;
      line-height: 3rem;    }
  p {     margin: 0 0 3rem;    }
   .words:before {
      content: '';    position: absolute;      width: 4px;
      top: 0;      left: 30px;      bottom: 0;
      border: 1px solid;      border-color: transparent #efe4e4;    }
  </style>
<div class="words" contenteditable></div>

<script>
  window.SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;

  const recognition = new SpeechRecognition();
  recognition.interimResults = true; //  사용자 입력이 끝났는지
  recognition.lang = 'en-US'; // 언어설정부분으로 

  let p = document.createElement('p');
  const words = document.querySelector('.words');
  words.appendChild(p);

  recognition.addEventListener('result', e => {  // result라는 이벤트가 발생하면
    const transcript = Array.from(e.results)     // e의 값 results를 배열로 만들어서 한개의 글자들을 모아 한 단어가 되게한다.
      .map(result => result[0])
      .map(result => result.transcript)
      .join('');

      const poopScript = transcript.replace(/poop|poo|shit|dump/gi, '💩');  // 이런말이 들어오면 💩 대치 
      p.textContent = poopScript;

      if (e.results[0].isFinal) {  // 음성인식의 끝인지를 검사한다. 아마 한글자를 입력했을때를 위해
        p = document.createElement('p');  
        words.appendChild(p);
      }
  });

  recognition.addEventListener('end', recognition.start);

  recognition.start();

</script>
```


