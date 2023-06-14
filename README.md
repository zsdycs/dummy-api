# dummy-api

## 启动顺序

- `npm install`
- `npm run start`

## 说明

- 在 dummy api 新设的情况下，向 route.json 追加下述结构

 ```javascript
{
  "request": {                                       // request 请求体
    "url": "^/api/auth/login$",                      // 设 url
    "method": "POST",                                // method
    "headers": {                                     // headers
      "Content-Type": "application/json"
    },
    "json": '{ "id": "b", "password": "b" }'         // body
  },
  "response": {                                      // response 响应体
    "status": 200,
    "headers": {
      "Content-Type": "text/html"
    },
    "file": "fixture/auth/login/TC001/response.json" // 用于读取 response 的文件
  }
},
 ```

- fixture 结构
  - `auth/login` : 与 API 根目录匹配的文件夹
  - `TC001` : 方案文件夹
  - `response.json` : 假设应答的 json 文件

## 其他

- [参考文档](https://github.com/mrak/stubby4node)
- 如果需要响应延迟，请参照下述内容：

 ```javascript
  "response": {
        "latency": 10000,
  }
 ```
