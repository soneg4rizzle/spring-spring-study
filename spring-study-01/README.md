## 🌱스프링 스터디-01
![image](https://user-images.githubusercontent.com/96826443/225811726-d7639b0b-8d65-43c0-a5fe-5ee174763f12.png)  
본 내용은 [인프런-스프링 입문] 강의를 들으며 공부한 내용 정리를 위한 리드미입니다. [강의링크](https://www.inflearn.com/course/lecture?courseSlug=%EC%8A%A4%ED%94%84%EB%A7%81-%EC%9E%85%EB%AC%B8-%EC%8A%A4%ED%94%84%EB%A7%81%EB%B6%80%ED%8A%B8&unitId=48553&category=chatDetail)


## 스프링 실습을 위한 초기 설정
![image](https://user-images.githubusercontent.com/96826443/225812388-2584a766-3f7d-4e84-bbe6-c7eaae8db8cf.png)  

* MAVEN PROJECT vs GRADLE PROJECT  
> [공통] 필요한 라이브러리를 가져와서 빌드 라이프 사이클을 관리해주는 툴  
> 과거에는 MAVEN을 많이 썼지만, 최근에는 GRADLE을 이용하는 추세이다.  
> 스프링 라이브러리 관리 자체도 GRADLE을 많이 사용하고 있다.  


* 강의에서는 JAVA JDK11, 스프링부트 2.3.1 버전을 사용했지만 시간이 지나 버전이 바뀌어 필자는 JDK17, 스프링부트 3.0.4 버전으로 실습을 진행했다.  
* Dependencies(Spring Web, Thymleaf 사용)  

## 인텔리제이로 프로젝트 빌드
![image](https://user-images.githubusercontent.com/96826443/225813112-092018bb-5cbd-45b4-90ba-4d1cf9b630db.png)

> .idea : 인텔리제이가 사용하는 설정 파일  
> gradle/wrapper : gradle 관련 사용 되는 폴더  
> src/test : 테스트 코드를 위해 존재하는 폴더(최근 테스트 코드 중요도가 올라가고 있다.)  
> src/main/java : 실제 패키지/소스파일이 들어있는 폴더  
> src/main/resources : 실제 자바 코드파일을 제외한 XML, properties(설정파일), html 등의 파일들이 존재한다(java file 제외)  
> build.gradle[중요] : plugin, repository, dependency, test 등의 설정을 관장하는 파일(버전 설정 및 라이브러리 사용(?))  
> gitignore : 소스코드 관리를 위한 파일(필요한 소스파일 정보만 올라가게 한다.(빌드 결과물은 X)  
 
 ## 스프링 부트 애플리케이션 실행
 ![image](https://user-images.githubusercontent.com/96826443/225814391-abe50947-4353-47ad-bbf6-14343f60cb8e.png)
![image](https://user-images.githubusercontent.com/96826443/225814492-6c4514d0-b11f-4837-a8b2-0300257b4eaa.png)
![image](https://user-images.githubusercontent.com/96826443/225814563-611ee64a-5dc2-4048-a3f2-e3c1abf42964.png)

> Tomcat started on port(s): 8080 : 뭔진 모르지만 톰캣이 포트 8080 시작했단다?  
> 찾아보니 톰캣(Apache Tomcat)은 웹 애플리케이션 서버인데 웹 서버와 연동해서 실행할 수 있는 자바 환경을 제공해준다고 한다. 동적 웹을 만들기 위한 웹 컨테이너라고 하는데 자세한 내용은 강의를 더 들어봐야 알 것 같다.  
> 간단한 동작 원리 : main 메소드 실행되면 스프링 부트 애플리케이션이 실행된다. 홈페이지가 웹 서버를 내장하고 있어 자체적으로 웹 사이트를 띄우며 스프링부트가 같이 올라간다고 한다.  


### 번외
![image](https://user-images.githubusercontent.com/96826443/225815807-9b1cf582-0caf-4f62-9456-81772a653e3a.png)

> 인텔리제이를 쓰면 빌드가 자바를 직접 실행하는게 아니라 Gradle을 통해서 실행될 때가 있다고 한다.  
> 윈도우기준 [FILE - SETTINGS : Build, Execution, Deplyment]에서 Build and run using/Run tests using을 Gradle에서 Intellij로 변경해준다.  
> Gradle을 경유해서 실행하는게 아니라 인텔리제이에서 자바로 바로 띄워주기 때문에 더 빠른 속도로 띄울 수 있다.

### 끝
