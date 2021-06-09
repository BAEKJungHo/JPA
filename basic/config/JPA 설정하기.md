# JPA 설정하기

- persistence.xml : JPA 설정 파일
  - /META-INF/persistence.xml 위치
  - persistence-unit name 으로 이름 지정
  - javax.persistence로 시작 : JPA 표준 속성
  - hibernate로 시작 : 하이버네이트 전용 속성

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<persistence version="2.2" 
 xmlns="http://xmlns.jcp.org/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
 xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence http://xmlns.jcp.org/xml/ns/persistence/persistence_2_2.xsd"> 
 <persistence-unit name="hello"> 
     <properties> 
     <!-- 필수 속성 --> 
     <property name="javax.persistence.jdbc.driver" value="org.h2.Driver"/> 
     <property name="javax.persistence.jdbc.user" value="sa"/> 
     <property name="javax.persistence.jdbc.password" value=""/> 
     <property name="javax.persistence.jdbc.url" value="jdbc:h2:tcp://localhost/~/test"/> 
     <property name="hibernate.dialect" value="org.hibernate.dialect.H2Dialect"/> 

     <!-- 옵션 --> 
     <property name="hibernate.show_sql" value="true"/> 
     <property name="hibernate.format_sql" value="true"/> 
     <property name="hibernate.use_sql_comments" value="true"/> 
     <!--<property name="hibernate.hbm2ddl.auto" value="create" />--> 
     </properties> 
 </persistence-unit> 
</persistence>
```
