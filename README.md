##### 🍑  Front_End 과정 1단계 

#### writing-mode Property     
살짝 헷갈릴 수 있는 내용입니다. horizontal이라면 일반적인 경우로 해석됩니다.    
왼쪽 --> 오른쪽,   
위--> 아래   
vertical로 적혀있다면 vertical 뒤에 있는 rl 또는 lr 가 방향을 결정한다고 생각하면 됩니다.    

writing-mode의 속성은 
Property Values

| value | 설명 |
|---|---|
| horizontal-tb | 	Let the content flow horizontally from left to right, vertically from top to bottom	 |
| vertical-rl |	Let the content flow vertically from top to bottom, horizontally from right to left	|
| vertical-lr	| Let the content flow vertically from top to bottom, horizontally from left to right |


horizontal-tb : 수평적으로하면 왼쪽 --> 오른쪽, 수직적으로는 위 --> 아래     
vertical-rl : 수평적으로 오른쪽--> 왼쪽, 수직적으로는 위--> 아래    
vertical-lr : 수평적으로 왼쪽--> 오른쪽, 수직적으로 위 --> 아래    
