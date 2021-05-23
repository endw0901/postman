# 配列でworkflow制御

```
// body
{
  "name": {{company}}
}

// pre request 

var companies = pm.environment.get("companies");

if(!pm.environment.get("companies")) {
  companies = ["google", "Yahoo", "Facebook", "Amazon"];
}

// 最初の要素を削除
const currentCompany = companies.shift();
pm.environment.set("company", currentCompany);
pm.environment.set("companies", companies);


// test
var companies = pm.environment.get("companies");

if(companies && companies.length > 0) {
  postman.setNextRequest("Request1");
} else {
  postman.setNextRequest(null);
}


```
