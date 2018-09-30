#### 4.4 离线组装删除共识节点交易

接口

**` Result createStopAgentTransaction(Output output) `**

说明

> 离线组装删除共识节点交易
>
> Result.data `String` 16进制后的交易序列化字符串

<table>
<tr>
<th align="center">参数</th>
<th align="center">类型</th>
<th align="center">是否必填</th>
<th align="center">说明</th>
</tr>
<tr>
<td align="center">output</td>
<td align="center">Object</td>
<td align="center">必填</td>
<td align="center">创建节点时被锁定的那条output</td>
</tr>
</table>

*e.g 示例代码*

```java
//创建节点交易被打包后，有一条lockTime = -1的output记录，就是用户创建节点被锁定的保证金，
//将output作为参数，生成退出委托共识交易
Output output = new Output();
output.setTxHash("0020b0a75a26caad17b4ea6cec7f059ac0e426d71696a6096f75bb2e9f30c11c60d6");
output.setIndex(0);
output.setValue(20000000000000L);
output.setAddress("Nse5x9foSzFjuwkwZLSvSjAHHLVf3MKJ");
output.setLockTime(-1);

Result result = NulsSDKTool.createStopAgentTransaction(output);
Map<String, Object> map = (Map<String, Object>) result.getData();
String txHex = (String) map.get("value");
```
