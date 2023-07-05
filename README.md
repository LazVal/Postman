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
```javascript 
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
### /object_info_4
23. Спарсить response body в json.

```javascript let resp_json = pm.response.json()
24. Спарсить request.
```javascript 
let req_param = pm.request.url.query.toObject()
```
25. Проверить, что name в ответе равно name s request (name забрать из request.)
```javascript 
pm.test("Name_resp=Name_req", function(){
    pm.expect(resp_json.name).to.eql(req_param.name)
});
```
26. Проверить, что age в ответе равно age из request (age забрать из request.)
```javascript 
pm.test("Age_resp=Agee_req", function(){
    pm.expect(+resp_json.age).to.eql(+req_param.age)
});
```
27. Вывести в консоль параметр salary из request.
```javascript 
console.log(req_param.salary)
```
28. Вывести в консоль параметр salary из response.
```javascript 
console.log(resp_json.salary)
```
29. Вывести в консоль 0-й элемент параметра salary из response.
```javascript 
console.log(resp_json.salary[0])
```
30. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```javascript 
console.log(resp_json.salary[1])
```
31. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```javascript 
console.log(resp_json.salary[2])
```
32. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```javascript 
pm.test("Salary_resp[0]=Salary_req", function(){
    pm.expect(+resp_json.salary[0]).to.eql(+req_param.salary)
});
```
33. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```javascript 
pm.test("Salary_resp[1]=Salary_req", function(){
    pm.expect(+resp_json.salary[1]).to.eql(+req_param.salary*2)
});
```
34. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```javascript 
pm.test("Salary_resp[2]=Salary_req", function(){
    pm.expect(+resp_json.salary[2]).to.eql(+req_param.salary*3)
});
```
35. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```javascript 
for (var i = 0; i<resp_json.salary.length;i++){
    console.log("salary= " +resp_json.salary[i]);
}
```
36. Передать в окружение переменную name1
```javascript 
pm.environment.set("name_1", resp_json.name);
```
37. Передать в окружение переменную age1
```javascript 
pm.environment.set("name_1", resp_json.age);
```
38. Передать в окружение переменную salary1
```javascript 
pm.environment.set("name_1", resp_json.age);
```
### /user_info_2
39. Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```javascript 
for (var i = 0 in resp_json.person){
    console.log("person: "+resp_json.person[i]);
}
```
40. Написать цикл который выведет в консоль по порядку элементы списка + значения из параметра person.
```javascript 
for (var key of Object.keys(resp_json.person)) {
    console.log(key + " -> " + resp_json.person[key])
}
```
## HOMEWORK 3
1) необходимо залогиниться
Приходящий токен необходимо передать во все остальные запросы.
Дальше все запросы требуют наличие токена.
```javascript 
token = pm.response.json().token
pm.environment.set("token", token);
```
2) Проверка структуры json в ответе.
```javascript
pm.test("Resp is JSON", function(){
    pm.response.to.be.json
});
let  schema = {
    "type":"object",
    "properties":{
        "person":{
            "type":"object",
            "properties":{
                 "u_age":{
                    "type":"integer",
                },
                "u_name":{
                    "type":"array",
                },
                "u_salary_1_5_year":{
                    "type":"integer",
                },
        },
        "required":["u_age","u_name", "u_salary_1_5_year"]
        },
        "qa_salary_after_12_months":{
            "type:":"number"
        },
         "qa_salary_after_6_months":{
            "type:":"number"
        },
         "start_qa_salary":{
            "type:":"number"
        },

    },
    "required":["person","qa_salary_after_12_months", "qa_salary_after_6_months","start_qa_salary"]
    
};
pm.test('Schema is valid', function() {
  pm.response.to.have.jsonSchema(schema);
});

tv4.setErrorReporter(function(error) {
    return "Error in here: " + error.resp_jsonPath + "in schema "
    + error.schemaPath;
});

pm.test("Verify that all values are correct", function(){
    var res = (tv4.validateMultiple(resp_json, schema, false, true));
    if(!res.valid){
        for(const error of res.errors){
            console.log("Validation failed", error)
        }
    }
    pm.expect(res.valid).to.be.true;
});
```
