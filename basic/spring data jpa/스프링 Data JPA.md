# 스프링 Data JPA

```java
@Configuration
@EnableJpaRepositories(basePackages = "com.gymzzak.pt.domain.*.repository")
@EnableJpaAuditing
public class JpaConfig {
}
```

스프링 데이터 JPA 는 애플리케이션을 실행할 때 basePackage 에 있는 리포지토리 인터페이스들을 찾아서 해당 인터페이스를 구현한 클래스를 동적으로 생성한 다음 스프링 빈으로 등록한다.
따라서 개발자가 직접 구현 클래스를 만들지 않아도 된다.

```java
public interface PrivacyRepository extends JpaRepository<Privacy, Long> {
}
```
