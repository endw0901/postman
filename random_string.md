# random string

```
https://httpbin.org/uuid

//test
let response = pm.response.json();
pm.globals.set("uuid", response.uuid);

// 次のrequestのbodyで変数で受け取る
{
    "name":"John",
    "email": "john@example.com",
    "id": "{{uuid}}"
}

```
