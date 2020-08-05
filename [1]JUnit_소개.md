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

## 3. JUnit 5 : 테스트 이름 표기하기

### `@DisplayNameGeneration`

- 기본적으로 Test 이름을 표기하는 방식 : 테스트 메소드 이름이 그대로 출력됨
  - 대부분 _ 을 이용하여 create_new_study 로 표기
- Method와 Class 레퍼런스를 사용해서 테스트 이름을 표기하는 방법 설정
  - class에 표기하면 클래스 내의 모든 테스트 메소드에 적용됨
  - 표기 시 전략을 설정할 수 있음
- 기본 구현체로 ReplaceUnderscores 제공

```java
package com.yegenieee.inflearnthejavatest;

import org.junit.jupiter.api.*;

import static org.junit.jupiter.api.Assertions.*;
@DisplayNameGeneration(DisplayNameGenerator.ReplaceUnderscores.class)
// underscore를 빈 칸으로 대체해줌
class StudyTest {

    @Test
  	@Disabled
    void create_new_study() {
				System.out.println("create new study method");
    }

}
```

![image-20200805213347289](/Users/yegenieee/Desktop/the-java-test/the-java-test/image/[2]image-20200805213347289.png)

### `@DisplayName`

- 어떤 테스트인지 테스트 이름을 보다 쉽게 표현할 수 있는 방법을 제공하는 애노테이션.
- `@DisplayNameGeneration` 보다 우선 순위가 높다.

```java
package com.yegenieee.inflearnthejavatest;

import org.junit.jupiter.api.*;

import static org.junit.jupiter.api.Assertions.*;

class StudyTest {

    @Test
  	@DisplayName("스터디 만들기")
    void create_new_study() {
				System.out.println("create new study method");
    }

}
```

![image-20200805213601385](/Users/yegenieee/Desktop/the-java-test/the-java-test/image/[3]image-20200805213601385.png)

- DisplayName을 이용하는 것이 더 좋음



