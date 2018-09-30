#### 1.9 备份账户
接口

**`Result backupAccount(String address, String path, String password)`**   

说明

> 根据账户地址,密码以及输出地址备份账户(导出.keystore文件)，如果账户是加密的则导出的keystore是由当前密码加密的，导入时需要验证此时账户的密码
>
> Result 返回生成的文件地址

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
        <td align="center">path</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">将要存放备份文件的文件夹，传null时，将备份到NULS服务的当前目录 </td>
    </tr>
     <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">非必填</td>
        <td align="center">账户密码，如果账户没有加密则不填</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
	    "value": "/Users/lichao/Downloads/2ChDcC1nvki521xXhYAUzYXt4RLNULS.accountkeystore"
    }
}
```
*e.g 示例代码*

```java
//备份一个没有密码的账户至当前目录
backupAccount("2ChqBTvFXttQsghj8zQpcdv76TQU8G5", null);
//备份一个有密码的账户至/backup目录
backupAccount("2ChqBTvFXttQsghj8zQpcdv76TQU8G5", "/backup", "nuls123456");
```
---
