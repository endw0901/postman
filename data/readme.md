# data

- collection runnerでdataをselectして実行
- scriptの中ではiterationDataで参照可能

```
pm.iterationData.get("customerId")
```

- global > collection > environment > data > local

- 外部dataのmetaInfoをjsonオブジェクトとして変数にしてから格納 "metaInfo" : {{metaInfo}}

data
```
[
    {
        "customerId": 9000,
        "productId": 5,
        "status": 200,
        "isValid": "true",
        "expectedStatus": 200,
        "metaInfo": {
            "categoryId": 9347,
            "segmentId": 7833,
            "keywords": "foo, bar, foobar"
        }
    },
    {
        "customerId": 9001,
        "productId": 4,
        "status": 500,
        "isValid": "true",
        "expectedStatus": 500,
        "metaInfo": null
    },
    {
        "customerId": 9002,
        "productId": "3FOO",
        "isValid": "false",
        "status": 404,
        "expectedStatus": 404,
        "metaInfo": {
            "categoryId": 1111,
            "segmentId": 2222,
            "keywords": "foo, bar, foobar"
        }
    }
]
```
