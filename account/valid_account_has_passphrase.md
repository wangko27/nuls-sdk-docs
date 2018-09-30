#### 1.12 验证账户是否加密  
接口

**`Result isEncrypted(String address)`**

说明

> 验证账户是否加密
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
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{	//表示已加密
    "success": true,
    "data": {
		"value":true
    }
}
```
- 返回 未加密

```json
{
    "success": true,
     "data"：{
        "value": false
     }
}
```
- 返回错误的情况,例如参数错误

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
isEncrypted("2ChqBTvFXttQsghj8zQpcdv76TQU8G5");
```
---
