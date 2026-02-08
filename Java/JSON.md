### JSON (JavaScript Object Notation) -> JavaScript 对象表示法
- JSON 是轻量级的文本数据交换格式
- JSON 文件的文件类型是 .json
- JSON 文本的 MIME 类型是 application/json

### JSON 语法规则
- 数据在名称/值对中(key : value)
- 数据由逗号 , 分隔
- 使用斜杆 \ 来转义字符
- 大括号 {} 保存对象
- 中括号 [] 保存数组，数组可以包含多个对象

### JSON 名称
- 名称/值对包括字段名称（在双引号中），后面写一个冒号，然后是值：

``` "name" : "itworker"```

### JSON 值 value
- 数字（整数或浮点数） : `{ "age":30 }`
- 字符串（在双引号中） : `{ "name":"itworker" }`
- 逻辑值（true 或 false） : `{ "flag":true }`
- 对象（在大括号中） : `{key1 : value1, key2 : value2, ... keyN : valueN }`
- null : `{ "json":null }`
- 数组（在中括号中） : 
```
[
    { key1 : value1-1 , key2:value1-2 }, 
    { key1 : value2-1 , key2:value2-2 }, 
    { key1 : value3-1 , key2:value3-2 }, 
    ...
    { key1 : valueN-1 , key2:valueN-2 }, 
]
```
