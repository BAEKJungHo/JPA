# @Entity

- @Entity
  - 해당 애노테이션이 있어야 JPA 가 관리한다.
  - 속성
    - name : name 속성이 없는 경우 클래스 명으로 생성된다. 만약에 다른 패키지에서 같은 이름의 클래스가 존재하는 경우에는 name 속성을 지정해서 conflict 방지를 해야 한다.
  - final 클래스, enum, interface, inner 클래스에서는 사용할 수 없다.
  - 저장할 필드에 final 을 사용하면 안 된다.
  - 기본 생성자가 필수이다.

