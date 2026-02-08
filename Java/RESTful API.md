### REST（Representational State Transfer，表述性状态转移）

### RESTful API的核心原则
1. 资源与URI<br>
在REST中，所有事物都被抽象为资源，每个资源有唯一的标识符（URI）。

URI设计规范：
- 使用名词而非动词表示资源
- 使用复数形式命名集合
- 使用小写字母和连字符(-)
- 避免文件扩展名
```
/users             # 用户集合
/users/123         # ID为123的用户
/users/123/orders  # 用户123的订单集合
```

<img width="1080" height="422" alt="image" src="https://github.com/user-attachments/assets/3cc0c933-9d47-466c-8354-005df56f10ef" />

### API 的基本概念
API（Application Programming Interface，应用程序编程接口）就像是不同软件之间的"翻译官"。

### HTTP方法
|HTTP 方法|作用|用法|
|-|-|-|
|GET|获取数据|GET /api/users/123/orders|
|POST|创建数据|POST /api/users{json request}|
|PUT|更新数据|PUT /api/users/123{json request}
|PATCH|部分更新资源|-|
|DELETE|删除数据|DELETE /api/orders/456|

## HTTP CODE
|状态码|含义|说明|
|-|-|-|
|200|OK|请求成功|
|201|Created|资源创建成功|
|400|Bad Request|请求有误|
|401|Unauthorized|未授权|
|404|Not Found|资源不存在|
|500|Internal Server Error|服务器内部错误|

## Request 
- 查询参数
```javascript
// 分页
GET /api/users?page=1&limit=10
// 过滤
GET /api/users?status=active&city=beijing
// 排序
GET /api/users?sort=created_at&order=desc
// 搜索
GET /api/users?search=张三
```

- API 版本控制
```javascript
// URL 路径版本控制
GET /api/v1/users
GET /api/v2/users

// 请求头版本控制
GET /api/users
Accept: application/vnd.api+json;version=1
```

- GET 请求
```
// 请求
GET /api/users/123
Accept: application/json

// 响应
{
  "id": 123,
  "name": "张三",
  "email": "zhangsan@example.com",
  "createdAt": "2024-01-15T08:30:00Z"
}
```

- POST 请求
```
// 请求
POST /api/users
Content-Type: application/json

{
  "name": "李四",
  "email": "lisi@example.com",
  "password": "securePassword123"
}

// 响应
{
  "id": 124,
  "name": "李四",
  "email": "lisi@example.com",
  "createdAt": "2024-01-15T09:00:00Z",
  "message": "用户创建成功"
}
```

## response 
- 统一的响应格式
```
{
  "success": true,
  "data": {
    "id": 123,
    "name": "张三"
  },
  "message": "操作成功",
  "timestamp": "2024-01-15T08:30:00Z"
}
```

- 错误响应格式
```
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "输入数据验证失败",
    "details": [
      {
        "field": "email",
        "message": "邮箱格式不正确"
      }
    ]
  },
  "timestamp": "2024-01-15T08:30:00Z"
}
```

- 分页响应
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "用户1"
    },
    {
      "id": 2,
      "name": "用户2"
    }
  ],
  "pagination": {
    "currentPage": 1,
    "totalPages": 10,
    "totalItems": 100,
    "itemsPerPage": 10
  }
}
```

### 常见错误码设计
```
const ERROR_CODES = {
  // 4xx 客户端错误
  'VALIDATION_ERROR': 400,        // 数据验证失败
  'UNAUTHORIZED': 401,            // 未授权
  'FORBIDDEN': 403,              // 禁止访问
  'NOT_FOUND': 404,              // 资源不存在
  'METHOD_NOT_ALLOWED': 405,     // 方法不允许
  'CONFLICT': 409,               // 资源冲突
  
  // 5xx 服务器错误
  'INTERNAL_ERROR': 500,         // 内部服务器错误
  'SERVICE_UNAVAILABLE': 503     // 服务不可用
}
```
