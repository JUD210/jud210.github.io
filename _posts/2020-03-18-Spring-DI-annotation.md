---
title:  "[Spring] 의존객체 자동 주입: @Autowired, @Resource, @Inject, @Qualifier"
excerpt: "의존객체 자동 주입의 세 가지 방법 @Resource, @Autowired, @Inject 각각의 차이점을 비교 후 정리하였으며, 의존객체 선택법 @Qualifier 에 대한 설명도 추가하였다."
tags:
  - Spring
  - Annotation
  - Dependency Injection
categories:
  - Spring
date: 2020-03-18 21:40:56 +0900
last_modified_at: 2020-03-19 02:54:28 +0900
---
{{ page.excerpt }}

## 의존객체 자동 주입 (Automatic Dependency Injection)

- 스프링 설정파일에서 `<constructor-arg>` 혹은 `<property>` 태그로 의존 객체 대상을 명시하지 않아도 스프링 컨테이너가 자동적으로 의존 대상 객체를 찾아 해당 객체에 필요한 의존성을 주입하는 것을 말한다.
- 의존객체 자동 주입은 **@Autowired** / **@Resource** / **@Inject** 3개의 어노테이션을 활용하여 적용 가능하다.

## 의존객체 선택

- 의존객체 자동 주입을 어노테이션을 사용했을 때, 의존성 주입 대상이 되는 객체를 **단 하나**로 특정할 수 없다면, Exception이 뜨게 된다.
- 이를 방지하기 위해 **@Qualifier** 어노테이션을 사용하여 의존성이 주입 될 객체의 **아이디**나 **이름**을 지정할 수 있다.

### @Autowired

- 주입하려고 하는 객체(bean)의 타입이 일치하는지를 찾고 객체를 자동으로 주입한다.
- Type -> Name -> Qualifier -> Exception
  - 만약 타입이 일치하는 객체가 없다면, @Autowired 아래에 위치한 속성명과 일치하는 bean을 컨테이너에서 찾는다. 
  - 만약 이름이 일치하는 객체가 없다면, @Qualifier 어노테이션의 유무를 찾아 그 어노테이션이 붙은 속성에 의존성을 주입한다.
  - 만약 Qualifier 값과 일치하는 대상이 없다면, Exception을 발생시킨다.
- Spring 프레임워크에서만 지원

> example 1: OK

```xml
<bean id="wordDao" class="com.word.dao.WordDao" />

<!-- Manual Dependency Injection: constructor-arg 활용
<bean id="registerService" class="com.word.service.WordRegisterService">
  <constructor-arg ref="wordDao" />
</bean> 
-->

<!-- Automatic Dependency Injection: Annotation 활용 -->
<bean id="registerService" class="com.word.service.WordRegisterService" />
```

```java
public class WordSearchServiceUseAutowired {
    @Autowired
    private WordDao wordDao;
    ...
}
```

> example 2: OK

```xml
<bean id="wordDao1" class="com.word.dao.WordDao" />
<bean id="wordDao2" class="com.word.dao.WordDao" />
<bean id="wordDao3" class="com.word.dao.WordDao" />

<bean id="registerService" class="com.word.service.WordRegisterService" />
```

```java
public class WordSearchServiceUseAutowired {
    @Autowired
    @Qualifier("wordDao1")
    private WordDao wordDao;
    ...
}
```

> example 3: OK, but **NOT** recommended!

```xml
<bean id="wordDao" class="com.word.dao.WordDao" />
<bean id="wordDao2" class="com.word.dao.WordDao" />
<bean id="wordDao3" class="com.word.dao.WordDao" />

<bean id="registerService" class="com.word.service.WordRegisterService" />
```

```java
public class WordSearchServiceUseAutowired {
    @Autowired
    private WordDao wordDao;
    ...
    // Type -> Name -> Qualifier -> Exception
    // Type 매칭 결과: wordDao, wordDao1, wordDao2 (3개)
    // Name 매칭 결과: wordDao (1개: 특정 완료)
}
```

### @Resource

- 이름을 기준으로 객체를 찾는다. 만일 이름이 존재하지 않는다면 타입을 기준으로 자동적으로 객체를 찾아 주입한다. 마지막으로 @Qualifier 어노테이션의 유무를 판별한 후 그 어노테이션이 붙은 속성을 주입한다.
- Name -> Type -> Qualifier -> Exception
- Java EE(Enterprise Edition) 기본 지원

> example 1: OK

```xml
<bean id="wordDao" class="com.word.dao.WordDao" />

<bean id="registerService" class="com.word.service.WordRegisterService" />
```

```java
public class WordSearchServiceUseAutowired {
    @Resource
    private WordDao wordDao;
    ...
}
```

> example 2: OK

```xml
<bean id="wordDaoTest" class="com.word.dao.WordDao" />
<bean id="wordDaoReal" class="com.word.dao.WordDao" />

<bean id="registerService" class="com.word.service.WordRegisterService" />
```

```java
public class WordSearchServiceUseAutowired {
    @Resource(name="wordDaoTest")
    private WordDao wordDao;
    ...
}
```

### @Inject

- @Autowired와 흡사하나, 자동 주입할 bean객체를 찾는 순서가 다르다.
- 실무에서는 @Qualifier 어노테이션을 통해 명시적으로 어느 bean객체를 어느 속성에다 주입할 것인지를 명시하는 것이 올바른 습관이기에, 굳이 사용할 필요가 있을지는 의문.
- Type -> Qualifier -> Name -> Exception
- Java EE(Enterprise Edition) 기본 지원

> example

```xml
<bean id="wordDao" class="com.word.dao.WordDao" />

<bean id="registerService" class="com.word.service.WordRegisterService" />
```

```java
public class WordSearchServiceUseAutowired {
    @Inject
    private WordDao wordDao;
    ...
}
```

### 비교표

|             |               @Autowired               |               @Resource                |                @Inject                 |
| :---------: | :------------------------------------: | :------------------------------------: | :------------------------------------: |
|    지원     |            Spring framework            |                Java EE                 |          Java EE          도           |
| 연결 우선도 | Type -> Name -> Qualifier -> Exception | Name -> Type -> Qualifier -> Exception | Type -> Qualifier -> Name -> Exception |

## 관련된 Post

없음

## 참고 자료

<https://www.inflearn.com/course/%EC%8A%A4%ED%94%84%EB%A7%81-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC_renew/>  
<https://blog.naver.com/platinasnow/220053030295>  
<https://engkimbs.tistory.com/682>  
<https://workatit.tistory.com/21>  
<https://itjava.tistory.com/54>  
<https://www.baeldung.com/spring-annotations-resource-inject-autowire>
