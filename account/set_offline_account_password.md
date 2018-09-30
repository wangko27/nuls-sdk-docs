#### 1.16 设置离线账户密码
接口

**`Result setPasswordOffline(String address, String priKey, String password)`**

说明

> 设置离线账户密码, sdk中独立加密,不与NULS服务交互
>
> Result 返回加密后的私钥（encryptedPriKey）

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
        <td align="center">priKey</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">账户的私钥</td>
    </tr>
        <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">新密码, 密码长度8~20，需同时包含字母和数字，不能输入空格</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
    	"value":"a770c1886f566c973b6eb99543ef03825a89ed16e20d8dbe320aed64a85d5863ca23df43ef16ce0475424a49e192b6f9"
    }
}
```
*e.g 示例代码*

```java
setPasswordOffline("2CacFwqMwcJiGNNBwiwV7bCL7bjwNBr","00e4bfd347351ea899b5f0ae2c0a3e7a6951b202eaf72432d1a63a2dc85c59c82a","nuls123456");
```
---
