# newman
- CLIツール
- postman apiで自分のcollectionやenvironmentをcliで取得し、コマンドラインで実行できる

- [postman公式](https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/)

- [newman公式](https://github.com/postmanlabs/newman)
⇒ Using Newman with the Postman API

## start
- share collection => get link

```
// cli実行
newman run (上記リンク)

newman run (url) -e xxx_environment.json

例）
newman run https://www.getpostman.com/collections/08efa59cd7939bb82655 -e C:\Users\xxxxxxx\Downloads\httpbin-postman-tests-master\httpbin-postman-tests-master\production.postman_environment.json
```

## postman api
- [newman公式](https://github.com/postmanlabs/newman)
⇒ Using Newman with the Postman API
=> explore => postman api探す => get api key

keyname:cxmas-postman
key:
C:\Users\cxmas\key\postmankey


```
2 Fetch a list of your collections from: https://api.getpostman.com/collections?apikey=$apiKey

3 Get the collection link via it's uid: https://api.getpostman.com/collections/$uid?apikey=$apiKey

4 Obtain the environment URI from: https://api.getpostman.com/environments?apikey=$apiKey

5 Using the collection and environment URIs acquired in steps 3 and 4, run the collection as follows:

$ newman run "https://api.getpostman.com/collections/$uid?apikey=$apiKey" \
```
例）
上記の2、3で自分のapi-collectionからuidでnewman-test collectionを特定し、api-keyとnewman-testのenvironmentでnewman cliから実行

※environmentはこの例ではローカルのjsonから取得しているが、上記4でenvironment URIを取得も可能

```
newman run https://api.getpostman.com/collections/{{uid}}?apikey={{api-key}} -e C:\Users\{{username}}\Downloads\httpbin-postman-tests-master\httpbin-postman-tests-master\production.postman_environment.json
```

## run newman with docker
- https://github.com/postmanlabs/newman-docker
