##### 🍑  Front_End 과정 1단계 


## @container 
컨테이너 컨텍스트에 스타일을 적용하는 조건부 그룹 규칙이다.  
스타일 선언은 조건에 따라 필터링되고 조건이 true이면 컨테이너에 적용된다. 조건은 컨테이너 크기가 변경될 때 평가된다.  
스타일 선언은 해당 컨테이너의 컨텍스트에서만 유효하다. 즉, 컨테이너의 하위 요소들에게만 유효하다   

형식  
```
@container [ <container-name> ]? <container-condition> { <stylesheet> }
```

