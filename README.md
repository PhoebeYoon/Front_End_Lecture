##### 🍑  Front_End 과정 1단계 


### 1. width: min-content vs max-content vs fit-content   

min-content와 max-content는 상대값과 반대로 가용공간이 아닌 담고 있는 컨텐츠에 의해 width 값을 결정한다.
- min-content는 요소의 너비를 줄일 수 있을 만큼 줄이고 싶을때 사용한다. 최소너비는 해당 요소안에 있는 컨텐츠에 의해 좌우된다.   
- max-content는 요소의 너비를 최대로 넓히고 싶을때 사용할 수 있다. 이때 줄바꿈을 하지 않은 문장의 길이가 최대너비가 된다.
- fit-content는 위의 2개의 하이브리드처럼 작동한다. 가용너비가 충분할때는 max-content처럼, 가용너비가 부족하면 margin를 제외한 너비를 요소의 width로 사용한다. 
