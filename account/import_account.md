#### 1.10 导入账户
接口

**`Result importAccountByKeystore`**  

说明

> 根据keystore文件导入账户, 如果keystore文件是由加密的account备份生成的，则需要验证备份时账户的密码。
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
        <td align="center">path/fileReader</td>
        <td align="center">String/FileReader</td>
        <td align="center">必填</td>
        <td align="center">待导入的.keystore文件的url，或者由.keystore文件生成的FileReader对象</td>
    </tr>
    <tr>
        <td align="center">password</td>
        <td align="center">String</td>
        <td align="center">非必填</td>
        <td align="center">.keystore文件对应的账户密码，如果导出.keystore时对应账户没有加密则不填</td>
    </tr>
     <tr>
        <td align="center">overwrite</td>
        <td align="center">boolean</td>
        <td align="center">必填</td>
        <td align="center">true: 执行覆盖导入; false: 如果该账户已经在钱包里存在，将不执行导入操作，并返回错误提示。</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
    	"value":"2ChDcC1nvki521xXhYAUzYXt4RLNULS"
    }
}
```
*e.g 示例代码*

```java
//导入一个有密码的账户
importAccountByKeystore("/backup/XXXXXX.keystore", "nuls123456", true);
importAccountByKeystore(fileReader, "nuls123456", true);
//导入一个没有密码的账户
importAccountByKeystore("/backup/XXXXXX.keystore", false);
importAccountByKeystore(fileReader, false);
```
---
