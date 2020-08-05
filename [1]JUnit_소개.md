# JUnit 소개

# 학습목표

1. JUnit가 무엇인지 안다.



## 1. JUnit5 소개

- 자바 개발자가 가장 많이 사용하는 테스팅 프레임워크
- 자바 8 이상을 필요로 함

![image-20200804204822034](image/[1]_image-20200804204822034.png)

- JUnit Platform :  JUnit 테스트를 실행해주는 런처 제공, TestEngine API 제공
- Jupiter : TestEngine API 구현체로, JUnit 5를 제공
- Vintage : JUnit 4와 3을 지원하는 TestEngine 구현체

## 2. JUnit 5 시작하기

- Spring Initializer로 새로운 프로젝트 생성

  - 2.2+ 버전의 스프링 부트 프로젝트를 만든다면 기본으로 JUnit 5 의존성 추가됨

- 스프링 부트 프로젝트를 사용하지 않는다면?

  ```xml
  <dependency>
  	<groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-engine</artifactId>
    <version>5.5.2</version>
    <scope>test</scope>
  </dependency>
  ```

- 기본 애노테이션
  - @Test
  - @BeforeAll / @AfterAll
  - @BeforeEach / @AfterEach
  - @Disabled

