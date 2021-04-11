# @Column

- 필드를 컬럼에 매핑한다.
- name 속성을 사용해서 이름을 지정할 수도 있다.
- 필드에 매핑정보가 없으면(어노테이션을 생략하면) 필드명을 사용해서 컬럼명으로 매핑한다.

```java
@Entity
class Member {
  
  @Column(name = "name")
  private String userName;

}
```
