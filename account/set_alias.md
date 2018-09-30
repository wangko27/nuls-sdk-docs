#### 1.15 设置别名
接口

**`Result setAlias(String address, String alias, String password)`**

说明

> 为账户设置一个别名
>
> Result 返回设置别名的交易hash

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
        <td align="center">账户的地址</td>
    </tr>
     <tr>
        <td align="center">alias</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">待设置的别名名称</td>
    </tr>
        <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">密码</td>
        <td align="center">账户密码，如果账户没有加密则不填</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data":{		
		"value":"0020d7a69747778f6f02e2b0171640bc98aa19c53700988b7765c195ae691f3202c6"
	}
}
```
- 错误示例

```json
{
    "success": false,
     "data"：{
        "code": "ACT007",
        "msg": "The account already set an alias"
     }
}
```
*e.g 示例代码*

```java
setAlias("2ChqBTvFXttQsghj8zQpcdv76TQU8G5", "factory666", "NULS111111");
setAlias("2ChqBTvFXttQsghj8zQpcdv76TQU8G5", "factory666");
```
---
