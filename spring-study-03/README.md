## 🌱스프링 스터디-03 (View 환경설정)
![image](https://user-images.githubusercontent.com/96826443/225811726-d7639b0b-8d65-43c0-a5fe-5ee174763f12.png)  
본 내용은 [인프런-스프링 입문] 강의를 들으며 공부한 내용 정리를 위한 리드미입니다. [강의링크](https://www.inflearn.com/course/lecture?courseSlug=%EC%8A%A4%ED%94%84%EB%A7%81-%EC%9E%85%EB%AC%B8-%EC%8A%A4%ED%94%84%EB%A7%81%EB%B6%80%ED%8A%B8&unitId=49573&category=chatDetail&tab=curriculum)<br><br><br>

### 웹 페이지 만들기(Welcome Page)
![image](https://user-images.githubusercontent.com/96826443/225820440-c19d5e10-8479-4a49-87a3-fee164cc17bf.png)<br><br>

> 이전에 톰캣으로 홈페이지를 띄웠을 때는 화이트 라벨 페이지라는 문구만 뜨고 아무것도 존재하지 않았다.  
> 이걸 한번 꾸며보도록 하자 !
<br><br><br>

### HTML 파일 생성
![image](https://user-images.githubusercontent.com/96826443/225821205-3a1abc05-068a-4581-ba5c-49ce8e815cf2.png)<br><br>

> 앞선 게시글에서 언급했듯이, 인텔리제이에서 빌드를 하면 실제 페이지와 자바코드를 관장하는 main 폴더가 존재하는데,  
> resource/static 폴더에 html 파일을 만들면 자바 소스파일을 실행했을 때 자동으로 8080/웹서버와 HTML 파일이 연동된다.  
> 따라서 내가 HTML 파일을 작성하면 이전의 WHITE LABEL PAGE가 아닌 내가 작성한 HTML 웹페이지가 나오게 된다.<br><br>

* 서버를 킨 후에 localhost:8080 으로 접속 했을 때 나오는 페이지는 아래와 같습니다.
![image](https://user-images.githubusercontent.com/96826443/225821750-63e9d6e4-d02a-4f8d-8640-b0a0b50e5e13.png)<br><br>
* 정적 페이지는 내가 적어놓은 파일을 그냥 웹 서버가 웹 브라우저에 넘겨주기만 하는 것이라 별로 큰 의미가 없다.  
* 이를 유용하게 활용하려면 템플릿 엔진([thymleaf](https://www.thymeleaf.org/))를 사용하여 다양하게 페이지에 변화를 줄 수 있다.  
<br><br><br>

### Thymeleaf Template HTML(타임리프 템플릿을 이용한 웹 페이지)
![image](https://user-images.githubusercontent.com/96826443/225828496-73b853c5-c9b6-48b7-99ef-583d5fa94aea.png)<br><br>
![image](https://user-images.githubusercontent.com/96826443/225828547-4d2d2331-2aae-486b-b94e-c41fbcf21be4.png)<br><br>

> HelloController.java 파일에서 MVC 모델에 애트리뷰트를 추가한다.  
> 이 때 "data"는 타임리프 템플릿을 적용한 hello.html 파일에서 사용할 변수 이름이고  
> "hello!!" 는 해당 변수에 들어갈 값을 의미한다.  
> @GetMapping("hello") : HTTP GET 요청을 특정 핸들러 메소드에 맵핑하기위한 annotation을 의미한다.  
<br><br><br>


### 타임리프 템플릿 엔진 동작 확인
![image](https://user-images.githubusercontent.com/96826443/225829376-c652828d-2ef6-49e7-ae2d-21880709d6c2.png)<br><br>
> 1. 웹 브라우저(로컬호스트)에서 /hello 라고 던지면, 스프링 부트는 내장된 톰캣 서버에서 받는다.  
> 2. 톰캣 서버는 스프링에게 컨테이너에 GET으로 받은 값을 확인하고 맞으면 Hello method를 실행시킨다.  
> 3. model.addAttribute(key, value)를 통해 설정된 값은 hello.html 파일에 렌더링 된다.  
> 4. HelloSpringApplication java 파일을 실행하면 함수 내에서 입력받은 값이 페이지에 렌더링 된 모습을 확인할 수 있다.<br><br>

* hello() 함수에서의 리턴 값("hello")은 template/?.html 의 ?에 해당한다.  
* 컨트롤러에서 리턴 값으로 문자 반환 -> 뷰 리졸버(viewResolver)가 화면 찾고 처리
![image](https://user-images.githubusercontent.com/96826443/225830482-fbd4f132-bf81-4ea6-9340-1cb218dd9916.png)
