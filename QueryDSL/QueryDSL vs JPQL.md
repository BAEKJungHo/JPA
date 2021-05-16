# QueryDSL  vs JPQL

```java
@Test
public void startJPQL() {
    Member findMember = em.createQuery("select m from Member m where m.username = :username", Member.class)
            .setParameter("username", "member1")
            .getSingleResult();

    assertThat(findMember.getUsername()).isEqualTo("member1");
}

// QueryDSL 로 짜려면 JPAQueryFactory 로 시작해야 한다.
@Test
public void startQuerydsl() {
    JPAQueryFactory queryFactory = new JPAQueryFactory(em);
    QMember qMember = new QMember("m");

    Member findMember = queryFactory
            .select(qMember)
            .from(qMember)
            .where(qMember.username.eq("member1")) // 이렇게 짜도 jdbc 의 preparedStatement 를 사용하여 자동으로 파라미터가 바인딩 된다.
            .fetchOne();

    assertThat(findMember.getUsername()).isEqualTo("member1");
}
```

- `JPQL`
  - JPQL 의 단점은 쿼리 작성을 문자열로 작성하기 때문에 오타가 났을 때 런타임 시점에 버그가 잡힌다.
- `QueryDSL`
  - QueryDSL 은 쿼리를 자바 코드로 작성하기 때문에 컴파일 시점에 버그가 잡힌다. 또한 파라미터 바인딩을 jdbc 의 preparedStatement 를 사용하여 자동으로 해결해 준다.
