#### 1.6 根据账户别名获取账户地址
接口

**`Result getAddressByAlias(String alias)`**

说明
> 根据账户别名获取账户地址字符串
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
        <td align="center">alias</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">账户别名 </td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
    	"value": "2ChDcC1nvki521xXhYAUzYXt4RLNULS"
    }
}
```
*e.g 示例代码*

```java
 getAddressByAlias("factory666");
```
---
