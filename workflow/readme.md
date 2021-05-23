# workflow制御

- router scriptはcollection folderにある
- run collectionの画面でrouter.jsonのデータをselectして実行

- https://www.youtube.com/watch?v=FWYKOR0Zj28
- https://github.com/vdespa/postman-advanced-workflow-example

## router

```
postman.setNextRequest(getNextRequest());

function getNextRequest() {
    let routes;
    if (Array.isArray(pm.globals.get("remainingRoutes")) === true) {
        routes = pm.globals.get("remainingRoutes");
    } else {
        routes = pm.iterationData.get("routes");
    }
    
    const nextRequest = routes.shift();
    pm.globals.set("remainingRoutes", routes);
    
    if (nextRequest === undefined) {
        pm.globals.clear("remainingRoutes");
        return null;
    }
    
    return nextRequest;
}
```

## data
```
[
    {
        "routes": [
            "Request 1",
            "Request 2",
            "Request 3",
            "Request 4"
        ]
    },
    {
        "routes": [
            "Request 1",
            "Request 2",
            "Request 3",
            "Request 5"
        ]
    },
    {
        "routes": [
            "Request 1",
            "Request 3",
            "Request 2",
            "Request 6"
        ]
    }
]
```
