# apigateway-sb-ms

- pom.xml introduced webflux dependency
- application.properties
  - spring.cloud.gateway.discovery.locator.enabled=true
  - spring.cloud.gateway.discovery.locator.lower-case-service-id=true
- application.properties routing properties update
  - spring.cloud.gateway.routes[0].id=users-ws-api
  - spring.cloud.gateway.routes[0].uri=;b://users-ws
  - spring.cloud.gateway.routes[0].predicates[0]=Path=/users-ws/status-check
  - spring.cloud.gateway.routes[0].predicates[1]=Method=GET
  - spring.cloud.gateway.routes[0].filters[0]=RemoveRequestHeader=cookie
