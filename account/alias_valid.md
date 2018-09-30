#### 1.8 验证别名是否可以使用
接口

**`Result isAliasUsable(String alias)`**

说明
> 根据别名名称验证别名是否可用（是否没有被使用）
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
        <td align="center">alias</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">别名名称</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{	//表示别名可以使用
    "success": true,
    "data": {
		"value":true
    }
}
```
- 返回 别名不可用的情况

```json
{	//表示别名不可以使用
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
isAliasUsable("factory666");
```
---
