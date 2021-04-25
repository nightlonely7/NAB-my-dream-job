
This is my NAB java coding challenge project.

These are github repositories url for all services related:

- Product Service: https://github.com/nightlonely7/smart-choice-product-service
- Product Price Service: https://github.com/nightlonely7/smart-choice-product-price-service
- Log Service:
- Configuration: https://github.com/nightlonely7/nab-smart-choice-configuration


=========================================================


Project's ERD: 

![image](https://user-images.githubusercontent.com/41773948/116012384-5fd21800-a654-11eb-841a-e901870aac8a.png)


Project's Solution Diagram:

![image](https://user-images.githubusercontent.com/41773948/116012389-66608f80-a654-11eb-82e6-d7b53253ffa2.png)



=========================================================


Software development principles, patterns & practices being applied:

 - 3 layers : Controllers - Services - Repositories (this is too trivial).

 - Hexagonal pattern (applied for DTOs): all dtos is centred by Model DTO, no direct mapping from one another without Model DTO.

![image](https://user-images.githubusercontent.com/41773948/116012376-4af58480-a654-11eb-8dde-07633295ede0.png)

 - State pattern: all product price sync scheduled methods can be implemented differently based on partner.

![image](https://user-images.githubusercontent.com/41773948/116012851-4da5a900-a657-11eb-8d24-4a149599eec4.png)


 - SOLID (partially)


