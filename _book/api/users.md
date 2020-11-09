## 1. 个人中心
### 1.1 功能描述
获取个人中心。
### 1.2 请求说明
> 请求方式：GET<br>
请求URL ：[me/personal](#)

### 1.3 请求参数
无参数
### 1.4 返回结果
```json  
{
  "data": {
    "information": [
      {
        "avatar": "http://blog.minhow.com",
        "nickname": "minhow",
        "age": "25"
      }
    ],
    "news": [
      {
        "title": "minhow",
        "content": "I am MinHow"
      }
    ]
  },
  "code": "200",
  "msg": "SUCCESS"
}
``` 
### 1.5 返回参数
字段       |字段类型       |字段说明
------------|-----------|-----------
information       |array        |信息
avatar       |string        |头像地址
nickname       |string        |昵称
age       |int        |年龄
       |        |
news       |array        |消息列表  
title       |string        |标题
content       |string        |内容
每组数组用空行隔开
### 1.6 错误状态码
参见 [全局响应状态码说明](../introduction.html/#134-全局响应状态码说明)
