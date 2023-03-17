## 🌱스프링 스터디-02
![image](https://user-images.githubusercontent.com/96826443/225817336-3f3d4d84-f246-4506-8835-ee9389ba3d09.png)<br><br>
본 내용은 [인프런-스프링 입문] 강의를 들으며 공부한 내용 정리를 위한 리드미입니다. [강의링크](https://www.inflearn.com/course/lecture?courseSlug=%EC%8A%A4%ED%94%84%EB%A7%81-%EC%9E%85%EB%AC%B8-%EC%8A%A4%ED%94%84%EB%A7%81%EB%B6%80%ED%8A%B8&unitId=49571&category=chatDetail)

## 라이브러리 간 의존관계(?)
![image](https://user-images.githubusercontent.com/96826443/225817286-ab02c07a-1600-4511-b725-b3740ad41f36.png)<br><br>
![image](https://user-images.githubusercontent.com/96826443/225817507-d133c4ce-6280-40d0-b2a9-cf04e1229a83.png)<br><br>

> 지난 시간에 start.spring.io 에서 환경설정을 할 때 디펜던시에 Thymleaf와 Web Starter 를 추가했었는데 인텔리제이의 "External Libraries를 보면 내가 추가하지 않은 라이브러리도 존재하는 것을 볼 수 있다.  
> 이유는 해당 라이브러리를 사용하기 위해 필요한 것들을 Gradle에서 자동으로 끌어와서 추가해주기 때문이다.<br><br>

![image](https://user-images.githubusercontent.com/96826443/225817765-099c74bd-6b61-4643-b9de-9e23b2f1cc27.png)<br><br>
![image](https://user-images.githubusercontent.com/96826443/225817992-1eebb04f-81a5-4527-9990-fdccbf321119.png)<br><br>
![image](https://user-images.githubusercontent.com/96826443/225818068-cce85327-c720-4fb7-aea8-202bcb6ed333.png)<br><br>

> 이러한 라이브러리 간의 의존관계는 해당 이미지를 통해 확인할 수 있다.  
> 스프링부트와 관련된 라이브러리를 쓰면 스프링 코어까지 모두 가져와서 세팅이 된다. (좀 편한데?)  


### 스프링 스타터 로깅(spring-starter-logging)
* slf4j vs logback  
> SLF4J는 Simple Logging Facade for Java의 약자로 라이브러리 인터페이스 역할  
> Logback이 실질적인 로깅 라이브러리 구현체로 SLF4J는 Logback를 사용하기 쉽게 포장하는 역할  


### 스프링 테스트 라이브러리(spring-test-library)
![image](https://user-images.githubusercontent.com/96826443/225819102-5abea658-0890-41d6-8cb6-29de4bcd7e5f.png)<br><br>

* spring-boot-starter-test
  * junit : 테스트 프레임워크(**핵심**)
  * mockito : 목 라이브러리
  * assertj : 테스트 코드를 편하게 작성하도록 도와주는 라이브러리
  * spring-test : 스프링 통합 테스트 지원 
### 스프링 부트 핵심 라이브러리(Spring-Boot Core-Library)
* spring-boot-starter-web  
  * spring-boot-starter-tomcat : 톰캣(웹서버)
  * spring-webmvc : 스프링 웹 MVC
* spring-boot-starter-thymleaf : 타임리프 템플릿 엔진(View)
* spring-boot-starter(공통) : 스프링 부트 + 스프링 코어 + 로깅
  * spring-boot
    * spring-core
  * spring-boot-starter-logging
    * logback, slf4j

### 끝
> 아직 무슨 소린지 모르겠다. 이런 라이브러리 쓰는구나~ 정도만 알고 나중에 실습할 때 정확히 채득하자.
