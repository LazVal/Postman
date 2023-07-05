# Postman

## HOMEWORK 1
### Создать запросы в Postman  [Collection](https://github.com/LazVal/Postman/blob/main/DZ.postman_collection.json) [Environment](https://github.com/LazVal/Postman/blob/main/DZ.postman_environment.json)

```Protocol: http
IP: 162.55.220.72
Port: 5005
```
## HOMEWORK 2

1. Проверить, что в body приходит правильный string.
```javascript
pm.test("Chek_string", function () {
    pm.expect(pm.response.text()).to.eql("This is the first responce from server!ss")
});
```
### /User_info_3
2. Спарсить response body в json.
```javascript
let resp_json = pm.response.json()
```
4. Спарсить request.
```javascript   
let req_f = request.data
```
5. Проверить, что name в ответе равно name s request (name вбить руками.)
```javascript 
pm.test("Name is equal", function() {
    pm.expect(resp_json.name).to.eql("Lena")
});
```
6. Проверить, что age в ответе равно age s request (age вбить руками.)
```javascript 
pm.test("Age is equal", function() {
    pm.expect(+resp_json.age).to.eql(30)
});
```
7. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```javascript 
pm.test("Salary is equal", function() {
    pm.expect(resp_json.salary).to.eql(250)
}) ;
```   
 8. Проверить, что name в ответе равно name s request (name забрать из request.)
```javascript 
 pm.test("Name_resp = Name_req", function() {
    pm.expect(resp_json.name).to.eql(req_f.name)
}) ;
```
9. Проверить, что age в ответе равно age s request (age забрать из request.)
 pm.test("Age_resp = Age_req", function() {
    pm.expect(+resp_json.age).to.eql(+req_f.age)
}) ;
```
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
pm.test("Salary_resp = Salary_req", function(){
    pm.expect(+resp_json.salary).to.eql(+req_f.salary)
});
```
11. Вывести в консоль параметр family из response.
```javascript 
console.log(resp_json.family)
```
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```javascript 
pm.test("u_salary_1_5_year = Salary_req*4", function(){
    pm.expect(+resp_json.family.u_salary_1_5_year).to.eql(+req_f.salary*4)
});
```
### /Object_info_3
13. Спарсить response body в json.
```javascript 
let resp_json = pm.response.json()
```
14. Спарсить request.
```javascript 
let req_param = pm.request.url.query.toObject()
```
15. Проверить, что name в ответе равно name s request (name забрать из request.)
```javascript 
pm.test("Name_resp=Name=req", function(){
    pm.expect(resp_json.name).to.eql(req_param.name)
});
```
16. Проверить, что age в ответе равно age s request (age забрать из request.)
```javascript 
pm.test("Age_resp=Age_req", function(){
    pm.expect(+resp_json.age).to.eql(+req_param.age)
});
```
17. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```javascript 
pm.test("Salary_resp=Salary_req", function(){
    pm.expect(+resp_json.salary).to.eql(+req_param.salary)
});
```
18. Вывести в консоль параметр family из response.
```javascript 
console.log(resp_json.family)
```
19. Проверить, что у параметра dog есть параметры name.
```javascript 
pm.test("Dog have a name", function(){
    pm.expect(resp_json.family.pets.dog).to.have.property('name')
});
```
20. Проверить, что у параметра dog есть параметры age.
```javascript 
pm.test("Dog have an age", function(){
    pm.expect(resp_json.family.pets.dog).to.have.property('age')
});
```
21. Проверить, что параметр name имеет значение Luky.
```javascript 
pm.test("Dog_name is equal Lucky", function(){
    pm.expect(resp_json.family.pets.dog.name).to.eql('Luky')
});
```
22. Проверить, что параметр age имеет значение 4.
```javascript 
pm.test("Age_dog = 4", function(){
    pm.expect(+resp_json.family.pets.dog.age).to.eql(4)
});
```
