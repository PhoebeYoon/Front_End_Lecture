# Front_End_Lecture

🦚 [form_practice.html]     
사용자 컴에 만듭니다   
``` html     
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html;charset=utf-8" >
    </head>
    <body>
        <fieldset>
            <legend>GET </legend>
            <form action="./form_practice_receiver.php" method="GET">
                <p>
                    Your name:
                    <input type="text" name="yourname" />
                </p>
                <p>
                    Job :
                    <select name="job">
                        <option value="designer">디자인너</option>
                        <option value="programmer">프로그래머</option>
                        <option value="planner">웹기획자</option>
                    </select>
                </p>
                <input type="submit" value="Send"/>
            </form>
        </fieldset>
        
        <fieldset>
            <legend>POST</legend>
            <form action="./form_practice_receiver.php" method="POST">
                <p>
                    Your name:
                    <input type="text" name="nickname">
                </p>
                <p>
                    Job :
                    <select name="job">
                        <option value="designer">디자이너</option>
                        <option value="programmer">프로그래머</option>
                        <option value="planner">웹기획자</option>
                    </select>
                </p>
                <input type="submit" value="Send"/>
            </form>
        </fieldset>
    </body>
</html>
```   

[form_receiver.php]     
서버에 올립니다 

``` php
<html>
        <head>
        <meta http-equiv="Content-Type" content="text/html;charset=utf-8" >
        </head>
        <body>
            <?php
            echo $_REQUEST['nickname'].'님의 profession은 '.$_REQUEST['job'].'이군요!';
            ?>
        </body>
</html>
````

접속할때는    
웹브라우저에  your Domain/folder이름/form_practice.html  로 접속합니다 

<img width="300" alt="스크린샷 2023-05-28 오후 3 12 24" src="https://github.com/PhoebeYoon/HTML_CSS/assets/48478079/70f0119e-1b82-4c1d-a725-287e181e36d6">


