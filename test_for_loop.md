# test for loop


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
