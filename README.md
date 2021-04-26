
This is my NAB Java coding challenge project.

These are GitHub repository URLs for all related services:

- Product Service: https://github.com/nightlonely7/smart-choice-product-service
- Product Price Service: https://github.com/nightlonely7/smart-choice-product-price-service
- Log Service: https://github.com/nightlonely7/nab-smart-choice-log-service
- Configuration: https://github.com/nightlonely7/nab-smart-choice-configuration


=========================================================


Project's ERD: 

![image](https://user-images.githubusercontent.com/41773948/116113156-6f983d80-a6e2-11eb-9dd4-751c5f3b1109.png)



Project's Solution Diagram:

![image](https://user-images.githubusercontent.com/41773948/116116722-aa4fa500-a6e5-11eb-8465-ea8404594f38.png)



Project's Architecture Diagram:

![image](https://user-images.githubusercontent.com/41773948/116112738-0adce300-a6e2-11eb-9c58-f8189f0623ee.png)



=========================================================


Software development principles, patterns & practices being applied:

 
 - 3 layers : Controllers - Services - Repositories (this is too trivial).

 - Hexagonal pattern (applied for DTOs): all DTOs is centred by Model DTOs, no direct mapping from one to another without mapping through Model DTOs (except client request/response DTOs).


![image](https://user-images.githubusercontent.com/41773948/116116201-18479c80-a6e5-11eb-8e1c-b5359e73efd9.png)

 
 - State pattern: all product price sync scheduled methods can be implemented differently based on partner.


![image](https://user-images.githubusercontent.com/41773948/116116459-62308280-a6e5-11eb-984f-196d7e243c37.png)
```java
    private final PartnerService tikiService;
    private final PartnerService lazadaService;
    private final PartnerService shopeeService;

    public PartnerService getPartnerService(PartnerEnum partnerEnum) {
        switch (partnerEnum) {
            case TIKI:
                return tikiService;
            case LAZADA:
                return lazadaService;
            case SHOPEE:
                return shopeeService;
            default:
                throw new IllegalStateException("Unexpected partnerEnum value: " + partnerEnum);
        }
    }
```

- S.O.L.I.D

========================================================

Folder structure and the key Java libraries and frameworks being used:

Folders:

| Folder  | Description |
| ------------- | ------------- |
| configuration  | Configuration classes for specific technologies configuration. |
| dto  | Contains DTOs (Data Transfer Object) as POJO Java class, there're sub folders corresponding to their functionality (httprequest, httpresponse, entity ...). |
| feignclient | Open Feign interfaces for REST Client implementation (see Open Feign Library below). |
| filter | Servlet filters. |
| input | Includes Http APIs, Events, Kafka Listeners, Schedulers, etc. They're application triggers, I put all of them in 'input' folder for practical uses. |
| property | Configurable properties, can be reloaded via refresh endpoint. |
| repository | Jpa Repository interfaces for Spring Data Jpa implementations. |
| service | Main logic computation here. |
| utility | Utility classes. |

Libraries/Frameworks:

| Library/Framework | Description |
| Spring Boot | Today's de-facto standard that Java applications cannot be without. |
| Spring Data Jpa | More abstraction above Hibernate ORM libs leads to faster development. |
| Open Feign | Makes writing java http clients easier and declaratively, especially in Spring Cloud environment via service-id mapping through Eureka, client-side load balancing, etc. |
| Spring Kafka | Spring's support library for Kafka Server. Kafka is an excellent message broker that can scale up easily in big microservice systems. |
| Spring Redis | Spring's support library for Redis Server. Redis is an in-memory data structure store, used as a database, cache, and message broker. I use it as a cache. |
| H2 Database | Embedded database for fast development only, not preferred for production. |
| Lombok | Reduces Java's boiler-plate codes like getters, setters. |
| Mapstruct | Auto mapping DTOs, which is essential when applying hexagonal pattern (you mapping DTOs a lot!). |
| Spring Cloud Counterparts (Config, Discovery Client, Gateway, Oauth2, etc) | Spring microservice's implementations. |
| Spring Actuator | Apply production-ready features like heath checking, restart, refresh configurations, shutdown, etc. |
| Spring Boot Devtools | Make it easier for developers. |

======================================================

Required steps in order to get the application run on a local computer:

(updating...)
