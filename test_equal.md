# test

```
// environmentでわける
if (pm.environment.get("environment") === 'prod') {
  // console.logは左下のconsoleから
  console.log(pm.environment.get("url"));
}
```

```
// ---------------------------
// eql, equal
// ---------------------------
pm.test("my test eql equal", function () {
  const a = {
    "name": "John"
  }
  const b = {
    "name": "John"
  }
  // error時のmessage引数つき
  pm.expect(a).to.eql(b, 'must be equal');

  // eqlは値が同じかどうか => a = b
  // equalは全く同じobjectかどうか。 => a ≠ b
  pm.expect(a).to.not.equal(b, '2');
});


// ---------------------------
// boolean
// ---------------------------
pm.test("my test to be", function () {
  pm.expect(true).to.be.true;
  pm.expect(false).to.be.false;
  pm.expect(null).to.be.null;
  pm.expect(undefined).to.be.undefined;

  // lengthよりemptyを使う
  pm.expect([]).to.be.empty;
  // pm.expect([].length).to.eql(0);
});


// ---------------------------
// 含む
// ---------------------------
pm.test("my test oneOf", function () {
  pm.expect(2).to.be.oneOf([1,2,3]);
  pm.expect('tanaka').to.match(/^ta/);
});


```
