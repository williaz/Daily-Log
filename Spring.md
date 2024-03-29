- [x] Spring Boot data.sql no loading
  - add ```spring.jpa.hibernate.ddl-auto=none```, else hibernate drop loaded data
- [x] JPA entity need a non-arg constructor explicitly
- [x] H2 console
  - ```spring.h2.console.enabled=true```
- [x] Security with Role
  - default “ROLE” prefix
  - think of each Role as a coarse-grained GrantedAuthority that is represented as a String and prefixed with “ROLE“. When using a Role directly, such as through an expression like hasRole(“ADMIN”), we are restricting access in a coarse-grained manner.
- [x] Security mvcMatchers("/user/**")
- to include subpath
- [x] Testing: @WebMvcTest only scan defined controller, have to provide @MockBean field for its dep
- [x] property class
  - main: @ConfigurationProperites(prefix = 'app.prop.prefield')
  - test: @RunWith @EnableConfigurationProperties @TestPropertySource("claspath:application-local.properties")
- [x] Spring cloud gateway, log routing
  - https://cloud.spring.io/spring-cloud-gateway/reference/html/#wiretap
```yml
logging:
  level:
    reactor:
      netty: INFO
    org:
      springframework:
        cloud:
          gateway: TRACE
spring:
  cloud:
    gateway:
      httpclient:
        wiretap: true
      httpserver:
        wiretap: true
```
- [ ] [request_rate_limiter.lua](https://github.com/spring-cloud/spring-cloud-gateway/blob/98b6ffda32941a313b97519ed24f7ab83f96e287/spring-cloud-gateway-server/src/main/resources/META-INF/scripts/request_rate_limiter.lua)
