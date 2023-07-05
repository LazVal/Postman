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
2. Спарсить response body в json.
```javascript
let resp_json = pm.response.json()
```
4. Спарсить request.
```javascript   
let req_f = request.data
```
//Проверить, что name в ответе равно name s request (name вбить руками.)
pm.test("Name is equal", function() {
    pm.expect(resp_json.name).to.eql("Lena")
});
//Проверить, что age в ответе равно age s request (age вбить руками.)
pm.test("Age is equal", function() {
    pm.expect(+resp_json.age).to.eql(30)
});
//Проверить, что salary в ответе равно salary s request (salary вбить руками.)
pm.test("Salary is equal", function() {
    pm.expect(resp_json.salary).to.eql(250)
}) ;   
 //Проверить, что name в ответе равно name s request (name забрать из request.)
 pm.test("Name_resp = Name_req", function() {
    pm.expect(resp_json.name).to.eql(req_f.name)
}) ;
//Проверить, что age в ответе равно age s request (age забрать из request.)
 pm.test("Age_resp = Age_req", function() {
    pm.expect(+resp_json.age).to.eql(+req_f.age)
}) ;
//Проверить, что salary в ответе равно salary s request (salary забрать из request.)
pm.test("Salary_resp = Salary_req", function(){
    pm.expect(+resp_json.salary).to.eql(+req_f.salary)
});
//Вывести в консоль параметр family из response.
console.log(resp_json.family)
//Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
pm.test("u_salary_1_5_year = Salary_req*4", function(){
    pm.expect(+resp_json.family.u_salary_1_5_year).to.eql(+req_f.salary*4)
});
