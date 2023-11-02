##### 🍑  Front_End 과정 1단계 

## css란
CSS의 가장 강력한 강점으로, CSS가 요소에 적용하려는 스타일의 우선순위를 정하는 데 사용하는 알고리즘입니다. 
CSS Cascade는 어떤 스타일을 적용할지 결정하기 위해 몇 가지 기준을 고려하는데, 그 기준은 다음과 같습니다.  

- Origin and Importance
- Context
- Style Attribute
- **Layers**
- Specificity(명시도)
- Order of Apperance(작성 순서)

CSS Cascade 기준은 높은 순위에서 낮은 순위로 순위가 매겨지며, 스타일이 각 기준에 따라 비교되었을 때 동등한 기준일 경우, 다음 기준으로 넘어가 비교합니다.  

개발자가 css를 작성할대 선택자를 과도하게 사용하거나 !import 를 사용하기도 하며 선택자를 적게 사용할 경우에 나중에 사용하는 명령문으로 쉽게 덮여쓸수도 있는 문제가 발생하여   

개발자가 이러한 딜레마를 쉽게 제어할 수 있도록 **CSS Cascade 알고리즘에 Cascade Layers라는 새로운 개념**이 도입되었다.


```
/* Cascade Layers 선언 예시 코드 */
/* 레이어 순서 정의 - 1. reset, 2. base, 3. theme */
@layer reset, base, theme;

 /* 첫번째 레이어 “reset” */
@layer reset { … }

/* 2번째 레이어 “base” */
@layer base { … }

/* 3번째 레이어 “theme” */
@layer theme { … }

/* base, theme, util 레이어 생성 */
@layer base, theme, util;

/* reset.css파일 전체가 이름없는 layer로 생성 */
@import url(reset.css) layer;

/* base.css파일 전체가 base 이름의 layer에 스타일이 추가 */
@import url(base.css) layer(base);

```
> 순서대로 reset, base, theme 레이어가 생성되ㅕ, 레이어가 늦게 생성될수록 스타일 우선권을 가집니다. 

### layer의 이름은 식별할 수 있도록 고유한 이름을 사용하시되 이름을 지정하지 않아도 됩니다. 이것을 익명 레이어라고 합니다.
```
/* reset.css 파일 전체가 익명 레이어1 로 생성 */
@import url(reset.css) layer;

/* base.css 파일 전체가 익명 레이어2 로 생성 */
@import url(base.css) layer;

/* 아래의 스타일을 가지는 익명 레이어3 생성 */
@layer {
  /* the next layer */
}

/* 아래의 스타일을 가지는 익명 레이어4 생성 */
@layer {
  /* and another */
}
```
### layer의 이름을 재사용할 수도 있다.
이런 경우에는 기존에 존재하던 레이어에 새로운 스타일이 추가된다고 보면 된다. 그러나 레이어의 적용순서에는 변화가 없다.
```
 /* 첫번째 레이어 “reset” */
@layer reset { … }

/* 2번째 레이어 “base” */
@layer base { … }

/* 3번째 레이어 “theme” */
@layer theme { … }

/* 2번째 레이어인 “base”에 스타일 추가 */
@layer base {
    * {
        color : red;
    }
}
```
그래서 아예 레이어의 순서를 따로 언급할 수도 있다.
```
/* 선언 순서에 따라 1. reset, 2.base, 3. theme, 4.util */
@layer reset, base, theme, util;
```
### revert-layer 
이것은 속성값으로 주어지는 것으로 'revert-layer' 라고 적어주면 된다. 즉 color:'revert-layer' 라고 적으면 이전 레이어순서에서 적용된 값으로 적용된다는 뜻이다. 

```html
@layer mylayer2, mylayer1; // mylayer1가 우선순위가 높다
@layer mylayer2 {
	.content {color: #00FFFF;   }
}

@layer mylayer1 {
	.content {color: #FF0000;background-color: #EAEAEA;}
 /* .goback { color: revert-layer}*/
// .goback 이라는 클래스를 가진 곳에는 이전 레이어 우선순위에 있는 것을 적용하라는 의미
}
p class="content">
    Lorem Ipsum is simply dummy text of the printing .
</p>
<p class="content goback">
    Lorem Ipsum is simply dummy text of the printing .
</p>
```
2개의 p가 모두 회색에 빨간색이지만 css의 .goback 주석을 해제하면 결과가 달라진다.
2번째 p는 color의 값을 적용할때 revert-layer라는 것이 적용되어 다음 mylayer2의 값이 적용된다. 

### 중첩레이어
```
@layer base { /* 첫번째 레이어 */
  p { max-width: 70px; }
}

@layer framework { /* 두번째 레이어 */
  @layer base { /* 두번째 레이어의 첫번째 레이어 */
    p { max-width: 100px; }
  }

  @layer theme { /* 두번째 레이어의 두번째 레이어 */
    p { color: #222; }
  }
}

```
위의 내용을 적용순서는 
1. base
2. framebark - 1. base > 2.theme



