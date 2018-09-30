#### 1.2 创建离线账户
接口

**`Result createOfflineAccount(int count, String password)`**

说明

> 直接离线创建一个账户并完整返回, 不会和NULS底层交互,不会进行持久化操作
> Create encrypted off-line accounts (Not saved to the database)
>
> Result.data <a href="#AccountInfo">`List<AccountInfo>`</a>

<table>
    <tr>
        <th align="center">参数</th>
        <th align="center">类型</th>
        <th align="center">是否必填</th>
        <th align="center">说明</th>
    </tr>
    <tr>
        <td align="center">count</td>
        <td align="center">int</td>
        <td align="center">非必填</td>
        <td align="center">创建账户的数量（默认1）</td>
    </tr>
     <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">非必填</td>
        <td align="center">设置账户密码, 密码长度8~20，需同时包含字母和数字，不能输入空格</td>
    </tr>
</table>   

返回结果  

- 返回结果为Result对象，格式如下：

```json
{
	"success": true,
	"data": {
		"list":[
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
				"address": "2CiBQg72BCLmLqttRpPfp8ECRCBwbdD",
				"alias": null,
				"pubKey": "020159dc5cc74463f346b71c08dd934a823e9e6fe727d8d3c577e7d462e1a364bb",
				"extend": null,
				"createTime": 1529314943624,
				"encrypted": true,
				"priKey": "",
				"encryptedPriKey": "5664f746654fb111e967bb3922910b16340f1e60ff1b281c7a333179d7b82d6220bb12d1c058d9cd06099d4f443a4cb0"
			}
		]
	}
}
```

*e.g 示例代码*

```java
//创建一个没有密码的离线账户
createOfflineAccount();
//创建一个有密码的离线账户
createOfflineAccount("nuls123456");
//创建3个没有密码的离线账户
createOfflineAccount(3);
//创建3个有密码的离线账户
createOfflineAccount(3, "nuls123456");
```

---
