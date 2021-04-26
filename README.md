
This is my NAB Java coding challenge project.

These are GitHub repository URLs for all related services:

- Product Service: https://github.com/nightlonely7/smart-choice-product-service
- Product Price Service: https://github.com/nightlonely7/smart-choice-product-price-service
- Log Service: https://github.com/nightlonely7/nab-smart-choice-log-service
- Configuration: https://github.com/nightlonely7/nab-smart-choice-configuration


=========================================================


Project's ERD: 

![image](https://user-images.githubusercontent.com/41773948/116013155-d3762400-a658-11eb-856f-f37731274d7b.png)



Project's Solution Diagram:

![image](https://user-images.githubusercontent.com/41773948/116012389-66608f80-a654-11eb-82e6-d7b53253ffa2.png)



Project's Architecture Diagram:

![image](https://user-images.githubusercontent.com/41773948/116112738-0adce300-a6e2-11eb-9c58-f8189f0623ee.png)



=========================================================


Software development principles, patterns & practices being applied:

 
 - 3 layers : Controllers - Services - Repositories (this is too trivial).

 - Hexagonal pattern (applied for DTOs): all DTOs is centred by Model DTOs, no direct mapping from one to another without mapping through Model DTOs (except client request/response DTOs).


![image](https://user-images.githubusercontent.com/41773948/116012376-4af58480-a654-11eb-8dde-07633295ede0.png)

 
 - State pattern: all product price sync scheduled methods can be implemented differently based on partner.


![image](https://user-images.githubusercontent.com/41773948/116015161-944cd080-a662-11eb-84c0-955ccb7298d8.png)


- S.O.L.I.D

========================================================

Folder structure and the key Java libraries and frameworks being used:

Folders:

- configuration: Configuration classes for specific technologies configuration.
- dto: contains DTOs (Data Transfer Object) as POJO Java class, there're sub folders corresponding to their functionality (httprequest, httpresponse, entity ...).
- feignclient: Open Feign interfaces for REST Client implementation (see Open Feign Library below).
- filter: Servlet filters.
- input: includes Http APIs, Events, Kafka Listeners, Schedulers, etc. They're application triggers, I put all of them in 'input' folder for practical uses.
- property: configurable properties, can be reloaded via refresh endpoint.
- repository: Jpa Repository interfaces for Spring Data Jpa implementations. 
- service: main logic computation here.
- utility: utility classes.

Libraries/Frameworks:

- Spring Boot: today's de-facto standard that Java applications cannot be without.
- Spring Data Jpa: more abstraction above Hibernate ORM libs leads to faster development.
- Open Feign: makes writing java http clients easier, especially in Spring Cloud environment via service-id mapping through Eureka, client-side load balancing, etc.
- Spring Kafka: Spring's support library for Kafka Server.
- Spring Redis: Spring's support library for Redis Server.
- H2 Database: embedded database for fast development only, not preferred for production.
- Lombok: reduces Java's boiler-plate codes like getters, setters.
- Mapstruct: auto mapping DTOs, which is essential when applying hexagonal pattern (you mapping DTOs a lot!).
- Spring Cloud Config, Discovery Client: part of Spring microservices implementations.
- Spring Actuator: apply production-ready features like heath checking, restart, refresh configurations, shutdown, etc.
- Spring Boot Devtools: make it easier for developers.


======================================================

Required steps in order to get the application run on a local computer:

(updating...)
