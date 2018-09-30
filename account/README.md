## 账户 AccountService
### 1.1 创建账户
接口

**`Result createAccount(int count, String password);`**

说明
> 创建账户可根据传入的参数创建单个或多个，有密码或没有密码的账户；
> 成功创建的账户信息将被持久化至NULS服务本地数据库中。
>
> 返回成功创建的账户地址集合

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

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data":{
	    "list": [ //返回创建账户的地址集合
	        "2Cbkwxu34iCjsiHKBjqZDNjoVbLMcJv",
	        "2Cbkwxu34iCjsiHKBjqZDNjoVbLMcJv"
	    ]
    }
}
```


*e.g 示例代码*

```java
//创建一个没有密码的账户
createAccount();
//创建一个有密码的账户
createAccount("nuls123456");
//创建3个没有密码的账户
createAccount(3);
//创建3个有密码的账户
createAccount(3, "nuls123456");
```
---
