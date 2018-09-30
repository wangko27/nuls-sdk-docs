#### 2.2 交易签名

接口

**`Result signTransaction(String txHex, String priKey, String address, String password)`**

说明

> 通过私钥，给交易签名
>
> Result.data `String` 签名后的交易，16进制后的序列化字符串

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
  <td align="center">十六进制的交易序列化数据</td>
  </tr>
   <tr>
  <td align="center">priKey</td>
  <td align="center">String</td>
  <td align="center">必填</td>
  <td align="center">交易的私钥</td>
  </tr>
   <tr>
  <td align="center">address</td>
  <td align="center">String</td>
  <td align="center">必填</td>
  <td align="center">私钥对应的地址，用于验证私钥合法性</td>
  </tr>
   <tr>
  <td align="center">password</td>
  <td align="center">String</td>
  <td align="center">非必填</td>
  <td align="center">私钥的密码，如果私钥未加密可不传</td>
  </tr>
  </table>

*e.g 示例代码*

```java
String txHex ="020197320f96301001a78cb7fb8bb7b1710b4afa390d8341080fba7a47e8d030000000000000000";
String priKey ="252f6d9d55b7ef539ea58df99ebaf71c9929bd9d0054338baf7a59c9b85b4fa631f816907c8";
String address = "2CXJEuoXZMajeTEgL6TgiSxTRRMwiMM";
String password = "NULS6352s!f";
Result result = NulsSDKTool.signTransaction(txHex, priKey, address, password);
```

>

---
