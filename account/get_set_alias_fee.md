#### 1.4 获取设置别名的手续费
接口

**`Result getAliasFee(String address, String alias)`**  

说明

>  根据账户地址和待设置的别名名称获取设置该别名所需要的手续费(不包含设置别名固定1NULS的花费)
>
>  Result.data `double`,  unit is `NULS`

**注意!** 此接口返回的手续费单位为`NULS`

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
    </tr></table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
	"success": true,
	"data":{
		"value": 0.01 //(单位为NULS)
	}
}
```

*e.g 示例代码*

```java
getAliasFee("2ChqBTvFXttQsghj8zQpcdv76TQU8G5","factory666");
```
---
