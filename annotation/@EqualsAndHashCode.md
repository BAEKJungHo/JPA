# @EqualsAndHashCode

@EqualsAndHashCode 는 롬복에서 제공하는 애노테이션이다.

하지만 JPA 사용시 자주 사용된다.

- `@EqualsAndHashCode`
  - equals(), hashCode() 를 생성해준다.
  - static or transient 가 아닌 모든 필드들이 대상이 된다.
  - 명시적으로 특정 필드를 제외하게 하려면 exclude={'field1', 'field2'}
  - 명시적으로 특정 필드를 포함하게 하려면 of={'field1'}
  - 기본적으로 getter 가 있으면 해당 메서드가 호출된다. 이를 사용하지 않고 필드를 직접 호출하려면 doNotUseGetter=true
  - `callSuper=true` 사용시 주의
    - SuperClass 가 없을 때(SuperClass 가 Object 일 때) 사용하면 컴파일 에러
    - SuperClass 도 lombok 을 사용했다면 문제가 되지 않지만, 그렇지 않다면 예상하지 못한 문제가 발생한다.

- `Tip`
  - `@EqualsAndHashCode(of="id")`
  - 연관 관계가 복잡해 질 때, @EqualsAndHashCode 에서 서로 다른 연관 관계를 순환 참조하느라 무한 루프가 발생하고, 결국 stack overflow 가 발생할 수 있기 때문에 id 값만 주로 사용

## References

> https://www.artima.com/articles/how-to-write-an-equality-method-in-java
