#### 2.4 转账
接口

**`Result transfer(String address, String toAddress, String password, long amount, String remark)`**

说明

> 发起转账交易
>
> Result 返回交易hash

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
        <td align="center">转出者账户的地址</td>
    </tr>
     <tr>
        <td align="center">toAddress</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">接收者账户的地址</td>
    </tr>
     <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">非必填</td>
        <td align="center">转出者账户的密码，如果账户没有加密则不填</td>
    </tr>
     <tr>
        <td align="center">amount</td>
        <td align="center">long</td>
        <td align="center">必填</td>
        <td align="center">转账金额(单位:Na)</td>
    </tr>
     <tr>
        <td align="center">remark</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">备注</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
    	"value":"00203a169b42e5e142e20b273ac925e55f773b5a38c5f5c907efdbc43abb7d7a67b2"
    }
}
```
*e.g 示例代码*

```java
	//账户有密码
transfer("2ChDcC1nvki521xXhYAUzYXt4RLNULS", "2CiU1CmB6c9jmSLDNBe6PouA7NgXXXX", "nuls123456", 8888800000000, "备注1NULS=10000000Na");
//账户没有密码
transfer("2ChDcC1nvki521xXhYAUzYXt4RLNULS", "2CiU1CmB6c9jmSLDNBe6PouA7NgNULS", 8888800000000, "备注1NULS=10000000Na");
```
---
