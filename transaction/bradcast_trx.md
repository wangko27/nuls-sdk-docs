#### 2.6 广播交易
接口

**`Result broadcastTransaction(String txHex);`**

说明

> 广播交易
>
> Result.data String 返回交易hash

<table>
    <tr>
        <th align="center">参数</th>
        <th align="center">类型</th>
        <th align="center">是否必填</th>
        <th align="center">说明</th>
    </tr>
    <tr>
        <td align="center">txHex</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">十六进制交易序列化数据</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
    	"value": "002023c66d10cf9047dbcca12aee2235ff9dfe0f13db3c921a2ec22e0dd63331cb85"
    }
}

```
*e.g 示例代码*

```java
String txHex = "1f9d3ad044e0e1201e117b041f3d2ceedacb44688e57969620f3ad7a4d6e9d241f9d3ad044e0e1201e117b041f3d2ceedacb44688e57969620f3ad7a4d6e9d24";
Result result = service.broadcastTransaction(txHex);
if(result.isSuccess()) {
   String txHash = (String)result.getData();
}
```
---
