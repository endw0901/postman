# postman
- collectionメニューからrun collection
- →結果の各行をクリックでbodyなどを見れる

- [postman公式ドキュメント](https://learning.postman.com/docs/writing-scripts/intro-to-scripts/)

## 変数・environment
- global < environment < data < local が優先（同じkey名のとき)
※dataはrunnerでiteration使うときだけ

- initial valueはteamにshareされるので、token等はcurrent valueのみに記載する

### url
get {{url}}/api/users
pm.variables.get('url')


## scripts
- pre-request => http request => tests
- console.logは左下のconsoleから

## test
- chai: https://www.chaijs.com/api/bdd/

## [Newman (CLI collection runner)](https://github.com/endw0901/postman/tree/main/newman)
```
npm install -g newman
```

## body
- ctrl + bで整形

## params
- valueはmouse overで [bar bar] => bar%20barとencodeできる

## create a request
- https://hookbin.com/
- api => 上記reloadで結果が出る

## post from import
- chrome F12 => network => right click menu => copy as cURL => import(raw text)
- [外部dataを使ってcollection runner](https://github.com/endw0901/postman/tree/main/data)

## trello api
e1db2ccbcacff83f8c55e4652d7ed926
tokenはtrelloのサイトでgenerate
https://trello.com/app-key

board作成
https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-post
