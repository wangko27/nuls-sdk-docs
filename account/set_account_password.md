#### 1.13 设置密码
接口

**`Result setPassword(String address, String password）`**

说明

> 为未加密的账户设置密码，已加密账户不能调用此接口
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
        <td align="center">必填</td>
        <td align="center">设置新密码, 密码长度8~20，需同时包含字母和数字，不能输入空格</td>
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
setPassword("2ChqBTvFXttQsghj8zQpcdv76TQU8G5", "nuls123456");
```
---
