# @MappedSuperclass

@MappedSuperclass 는 부모 클래스는 테이블과 매핑하지 않고 부모 클래스를 상속 받는 자식 클래스에게 매핑 정보만 제공할 때 사용한다.

@MappedSuperclass 는 추상 클래스와 비슷한데 @Entity 는 실제 테이블과 매핑되지만 @MappedSuperclass 는 실제 테이블과는 매핑되지 않는다. 즉, `상속 목적`으로만 사용한다.

> @MappedSuperclass 는 엔티티가 아니다. em.find() 나 JPQL 에서 사용할 수 없다.

@Entity 하위 클래스의 공통 속성들을 뽑아 @MappedSuperclass 가 적용된 추상 클래스를 만들어 상속 받아 사용하면된다.

부모로부터 물려받은 매핑 정보를 재정의하려면 `@AttributeOverrides` 나 `@AttributeOverride`를 사용하고 연관관계를 재정의하려면 `@AssociationOverrides` 나 `@AssociationOverride` 를 사용한다.
