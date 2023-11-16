##### 🍑  Front_End 과정 1단계 
## All about HTML5 & CSS3
참조 : 
- https://developer.mozilla.org/
- http://www.devdic.com/
- http://www.devdic.com/reference/css (css 레퍼런스) 
 

 
  

```
.person { }       <- Block: The sole root of the component.   
.person__head { } <- Element: A component part of the Block.  
.person--tall { }  <- Modifier: A variant or extension of the Block.  
```
Elements are delimited with two (2) underscores (__), and Modifiers are delimited by two (2) hyphens (--).   

Here we can see that    
.person {} is the Block; it is the sole root of a discrete entity.    
.person__head {} is an Element; it is a smaller part of the .person {} Block. Finally,   
.person--tall {} is a Modifier; it is a specific variant of the .person {} Block.    


위의 파일 fullstack-javascript.zip 에서 json 부분 다룰때  실행방법 
1. 터미널에서 npm install -g json-server
2. db.json
3. ```
   {
 "posts" :[{"id":1, "title":"json-server"}],
 "comments" : [{"id":1 , "body":"some comment"}],
 "profile":{"name":"ttt"}
}
```
4. json-server --watch db.json 실행 후 터미널 창에
```
 Resources
  http://localhost:3000/posts
  http://localhost:3000/comments
  http://localhost:3000/profile

  Home
  http://localhost:3000
  ```
출력된다.  

