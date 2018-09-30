#### 2.8 多地址转账交易签名

接口

**`Result signMultipleAddressTransaction(String txHex, List<String> privKeys, List<String> passwords)`**

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
  <td align="center">privKeys</td>
  <td align="center">List<String></String></td>
  <td align="center">必填</td>
  <td align="center">交易的私钥</td>
  </tr>
   <tr>
  <td align="center">passwords</td>
  <td align="center">List<String></String></td>
  <td align="center">必填</td>
  <td align="center">私钥对应的密码（多个账户密码必须一样）</td>
  </tr>
  </table>

*e.g 示例代码*

```java
String txHex ="020197320f96301001a78cb7fb8bb7b1710b4afa390d8341080fba7a47e8d030000000000000000";
List<String> priKeys = Arrays.asList("08a605b754bd1be1ba765fabd5cd218a545eb38b54ad26a7eb8a3378f724e5be", "00a710f9679fb6b5953bcfbea67a198e9c0d8888c43bad78a7241258e36aeaf65d");
List<String> passwords = Arrays.asList("123456","123456");
Result result = NulsSDKTool.signMultiTransaction(txHex, priKeys, passwords);
```
