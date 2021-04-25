
This is my NAB java coding challenge project.

These are github repositories url for all services related:

- Product Service: https://github.com/nightlonely7/smart-choice-product-service
- Product Price Service: https://github.com/nightlonely7/smart-choice-product-price-service
- Log Service:
- Configuration: https://github.com/nightlonely7/nab-smart-choice-configuration


=========================================================


Project's ERD: 

![image](https://user-images.githubusercontent.com/41773948/116013155-d3762400-a658-11eb-856f-f37731274d7b.png)



Project's Solution Diagram:

![image](https://user-images.githubusercontent.com/41773948/116012389-66608f80-a654-11eb-82e6-d7b53253ffa2.png)



=========================================================


Software development principles, patterns & practices being applied:

 - 3 layers : Controllers - Services - Repositories (this is too trivial).

 - Hexagonal pattern (applied for DTOs): all DTOs is centred by Model DTOs, no direct mapping from one to another without mapping through Model DTOs (except client request/response DTOs).

![image](https://user-images.githubusercontent.com/41773948/116012376-4af58480-a654-11eb-8dde-07633295ede0.png)

 - State pattern: all product price sync scheduled methods can be implemented differently based on partner.

![image](https://user-images.githubusercontent.com/41773948/116012851-4da5a900-a657-11eb-8d24-4a149599eec4.png)


 - S.O.L.I.D (partially)


