---
title: claudia rest api
category: framework / library
kind : claudiajs
order: 2
comments: true
---

## claudiajs : https://claudiajs.com

1. make project
2. install claudia api module
3. modify package.json script command
4. make api.js file
5. make api gateway
6. example code

### 1. make lambda project

```jshelllanguage
mkdir example
cd example
npm init
```

### 2. install claudia api module : https://claudiajs.com/claudia-api-builder.html

```jshelllanguage
npm install claudia-api-builder -S
```

### 3. modify package.json script command

package.json
```json
...
  "scripts": {
    "start": "claudia create --name rest-api-test --region ap-northeast-2 --api-module api --profile claudia",
    "deploy": "claudia update --profile claudia"
  },
...
```

### 4. make a api.js file : 
- https://github.com/claudiajs/claudia-api-builder/blob/master/docs/api.md#api-definition-syntax
- https://github.com/claudiajs/claudia-api-builder/blob/4f5c30df0365812765806ae2f9fd97e7a1287ed9/docs/api.md

```javascript
var ApiBuilder = require('claudia-api-builder'),
	api = new ApiBuilder(),
	superb = require('superb');

module.exports = api;

api.get('/greet', function (request) {
	return request.queryString.name + ' is ' + superb();
});
```

### 5. make api gateway : https://claudiajs.com/tutorials/hello-world-api-gateway.html

execute command

```jshelllanguage
#claudia create --name [lambda function name, api gateway name] --region [region name] --api-module [main javascript file name] --profile [profile name]
npm run start
```

you can see below console as result

saving configuration
```json
{
  "lambda": {
    "role": "rest-api-test-executor",
    "name": "rest-api-test",
    "region": "ap-northeast-2"
  },
  "api": {
    "id": "XXXXXXXX",
    "module": "api",
    "url": "https://XXXXXXXX.execute-api.ap-northeast-2.amazonaws.com/latest"
  }
}
```

you can connect to `api.url`

### 6. example code

[github](https://github.com/j2yes/lambda-rest-claudia)
