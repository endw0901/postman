# workflow

- https://github.com/endw0901/postman/tree/main/workflow
- [配列で制御](https://github.com/endw0901/postman/blob/main/workflow_array.md)

```
// workflow は1->3 -> 2の順に動き、next requestをnullにしておかないと、次の3に自動で進み、3-2-3-2の永久ループになる

console.log(pm.globals.get("runnedOnce"));

if (pm.globals.get("runnedOnce")) {
  postman.setNextRequest(null);
}

// グローバル変数の設定 ※次実行されるときに1が設定されているのでnullで止まる
pm.globals.set("runnedOnce", 1);



// グローバル変数の削除（テスト後のクリア）
// pm.globals.unset("boardId");


```
