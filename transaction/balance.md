#### 2.5 查询账户余额
接口

**`Result getBalance(String address)`**

说明

> 获取账户余额
>
> Result.data <a href="#BalanceInfo">`BalanceInfo `</a>

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
{
    "success": true,
    "data": {
        "balance": 1009899998900000,
        "usable": 1009899998900000,
        "locked": 0
    }
}
```
*e.g 示例代码*

```java
getBalance("2ChDcC1nvki521xXhYAUzYXt4RLNULS");
```
---
