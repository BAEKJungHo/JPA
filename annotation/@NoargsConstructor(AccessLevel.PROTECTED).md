# @NoargsConstructor(AccessLevel.PROTECTED)

Entity나 DTO를 사용할때 `@NoargsConstructor(AccessLevel.PROTECTED)` 어노테이션을 많이 사용하는 편입니다.

기본 생성자의 접근 제어를 PROTECTED로 설정해놓게 되면 무분별한 객체 생성에 대해 한번 더 체크할 수 있는 수단이 되기 때문입니다.

예를 들어 User라는 Class는 name, age, email 정보를 모두 가지고있어야만 되는 상황일경우에

기본 생성자를 막는것은 이를 도와주는 좋은 수단이 됩니다.

> setter 로 생성하게되는경우 개발자 실수로 누락을 하게될 수 있기 때문에,  불완전한 상태가 된다.

## References

> https://cobbybb.tistory.com/14
