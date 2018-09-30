#### 1.5 获取账户列表
接口

**`Result getAccountList(int pageNumber, int pageSize)`**

说明

> 根据分页参数获取账户列表
>
> Result.data Page <a href="#AccountInfo">`List<AccountInfo>`</a>

<table>
    <tr>
        <th align="center">参数</th>
        <th align="center">类型</th>
        <th align="center">是否必填</th>
        <th align="center">说明</th>
    </tr>
    <tr>
        <td align="center">pageNumber</td>
        <td align="center">int</td>
        <td align="center">必填</td>
        <td align="center">页码，必须大于0 </td>
    </tr>
    <tr>
        <td align="center">pageSize</td>
        <td align="center">int</td>
        <td align="center">必填</td>
        <td align="center">每页返回数据记录数量, 取值范围1~100</td>
    </tr></table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
	"success": true,
	"data": {
		"pageNumber": 1,
    	"pageSize": 10,
    	"total": 100,
     	"pages": 10,
		"list": [
			{
				"address": String, 账户地址
				"alias": String, 账户别名
				"pubKey": String, 公钥
				"extend": String, 扩展
				"createTime": Long, 创建时间
				"encrypted": boolean, 是否加密
				"priKey": String, 私钥（创建无密码离线账户时才会有值）
				"encryptedPriKey": String, 加密私钥（创建有密码离线账户时才会有值）
			},
			{
				"address": "2Cid96JrTGA2XaNG6zXrRKh18kLUbLP",
				"alias": null,
				"pubKey": "033da2433ef4ca111bfeefaadd9fe0f5874f3aac5186109f9de10a9eed6f48f184",
				"extend": null,
				"createTime": 1529311250627,
				"encrypted": true,
				"priKey": null,
				"encryptedPriKey": null
			}
			...

		]
	}
}
```

*e.g 示例代码*

```java
getAccountList(1, 10);
```
---
