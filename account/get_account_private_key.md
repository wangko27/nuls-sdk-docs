#### 1.7 获取账户私钥
接口

**`Result getPrikey(String address, String password)`**

说明
> 根据账户地址和密码获取账户私钥，返回私钥字符串
>
> Result.data `String`

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
{
    "success": true,
    "data": {
		"value":"1f9d3ad044e0e1201e117b041f3d2ceedacb44688e57969620f3ad7a4d6e9d24"
    }
}
```
*e.g 示例代码*

```java
//有密码的账户调用方式
getPrikey("2ChqBTvFXttQsghj8zQpcdv76TQU8G5", "nuls123456");
//无密码的账户调用方式
getPrikey("2ChqBTvFXttQsghj8zQpcdv76TQU8G5");
```
---
