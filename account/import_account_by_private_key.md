#### 1.11 导入账户(私钥)  
接口

**`Result importAccountByPriKey(String privateKey, String password, boolean overwrite)`**  

说明

> 根据私钥导入账户
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
        <td align="center">privateKey</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">账户私钥 </td>
    </tr>
    <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">非必填</td>
        <td align="center">设置新密码, 密码长度8~20，需同时包含字母和数字，不能输入空格</td>
    </tr>
     <tr>
        <td align="center">overwrite</td>
        <td align="center">boolean</td>
        <td align="center">必填</td>
        <td align="center">true: 执行覆盖导入; false: 如果该账户已经在钱包里存在，将不执行导入操作，并返回错误提示。</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
    	"value":"2CiU1CmB6c9jmSLDNBe6PouA7NgNULS"
    }
}
```
*e.g 示例代码*

```java
//导入账户时设置密码
importAccountByPriKey("1f9d3ad044e0e120......", "nuls123456", true);
//导入账户时不设置密码
importAccountByPriKey("1f9d3ad044e0e120......", true);
```
---
