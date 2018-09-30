#### 1.3 获取账户

接口

**`Result getAccount(String address)`**  

说明

>  根据账户地址获取一个账户的信息
>
>  Result.data <a href="#AccountInfo">`AccountInfo`</a>

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
    </table>

##### 返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
	"success": true,
	"data": {
		"address": String, 账户地址
		"alias": String, 账户别名
		"pubKey": String, 公钥
		"extend": String, 扩展
		"createTime": Long, 创建时间
		"encrypted": boolean, 是否加密
		"priKey": String, 私钥（创建无密码离线账户时才会有值）
		"encryptedPriKey": String, 加密私钥（创建有密码离线账户时才会有值）
	}
}
```

*e.g 示例代码*

```java
getAccount("2ChqBTvFXttQsghj8zQpcdv76TQU8G5");
```
---
