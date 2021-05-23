# test for loop

- https://github.com/endw0901/postman/tree/main/scripts_variables
- exapmle scripts & environment

```
//-----------------
// for loop & ifで対象を取得してテスト
//-----------------
for (let filter of jsonData.filters) {
  // console.log(filter);
  if(filter.name == "MANUFACTURER") {
    // console.log(filter);
    manufacturer = filter;

    pm.test("manufactuerer should not be allowed", function() {
      pm.expect(manufacturer.name).to.eql("MANUFACTURER");
      pm.expect(manufacturer.isAllowed).to.be.false;
    })
  }
}
```

## nested assertion

```
const jsonData = pm.response.json();

// console.log(typeof jsonData.prefs);
// console.log(jsonData.prefs.comments.status);

const commentsStatus = jsonData.prefs.comments.status;

pm.test("comment should be disabled", function() {
  pm.expect(commentsStatus).to.eql("disabled");
})

const boardStatus = jsonData.limits['54bba24af6196bd5f824e563'].boards.totalPerMember.status;

for (let key in jsonData.limits) {
  // console.log(key,jsonData.limits[key]);
  if (jsonData.limits[key].hasOwnProperty('boards')) {
    boardStatus = jsonData.limits[key].boards.totalPerMember.status;
  }
}

pm.test("boards should be ok", function() {
  pm.expect(boardStatus).to.eql("ok");
})

```
