#### 1.13 移除账户
接口

**`Result removeAccount(String address, String password)`**

说明

> 移除账户
>
> Result

<table>
    <tr>
        <th align="center">参数</th>
        <th align="center">类型</th>
        <th align="center">是否必填</th>
        <th align="center">说明</th>
    </tr>
    <tr>
        <td align="center">address</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">账户地址</td>
    </tr>
     <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">非必填</td>
        <td align="center">账户密码，如果账户没有加密则不填</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{	//表示成功
    "success": true,
    "data": {
		"value":true
    }
}
```

- 返回不成功 以及错误的情况,例如参数错误

```json
{	//表示错误的情况
    "success": false,
     "data"：{
        "code": "ACT005",
        "msg": "xxxxxx...."
     }
}
```
*e.g 示例代码*

```java
removeAccount("2ChqBTvFXttQsghj8zQpcdv76TQU8G5");
removeAccount("2ChqBTvFXttQsghj8zQpcdv76TQU8G5", "nuls123456");
```
---
