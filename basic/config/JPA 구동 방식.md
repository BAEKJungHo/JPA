# JPA 구동 방식

> JPA 는 특정 데이터베이스에 종속적이지 않다.

- 구동 방식
  1. 설정 정보 조회 : META-INF/persistence.xml
  2. Persistence -> EntityManagerFactory 생성 -> EntityManager 생성

- EntityManagerFactory
  - 하나만 생성해서 애플리케이션 전체에서 공유
- EntityManager
  - 쓰레드간에 공유 X(사용하고 버려야 한다.)
- JPA 의 모든 데이터 변경은 트랜잭션 안에서 진행

- `가장 기초적이고 정석적인 방식`

```java
public class JpaMain {

    private static final String persistenceUnitName = "hello";

    public static void main(String[] args) {
        EntityManagerFactory emf = Persistence.createEntityManagerFactory(persistenceUnitName);
        EntityManager em = emf.createEntityManager();

        // JPA 는 모두 Transcation 안에서 작동해야 한다.
        EntityTransaction tx = em.getTransaction();
        tx.begin();

        try {
            Member member = new Member();
            member.setId(1L);
            member.setName("HelloA");
            em.persist(member);

            tx.commit();
        } catch(Exception e) {
            tx.rollback();
        } finally {
            em.close();
        }

        emf.close();
    }

}

```
