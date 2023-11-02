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

