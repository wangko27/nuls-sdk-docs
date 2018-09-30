#### 4.2 离线组装委托共识交易

接口

**` Result createDepositTransaction(DepositInfo depositInfo, List<Input> inputs, Na fee) `**

说明

> 离线组装委托共识交易
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
<td align="center">depositInfo</td>
<td align="center">Object</td>
<td align="center">必填</td>
<td align="center">创建节点信息</td>
</tr>
<tr>
<td align="center">inputs</td>
<td align="center">List</td>
<td align="center">必填</td>
<td align="center">输入信息</td>
</tr>
<tr>
<td align="center">fee</td>
<td align="center">Object</td>
<td align="center">必填</td>
<td align="center">交易手续费</td>
</tr>
</table>

*e.g 示例代码*

```java
//组装交易的inputs,示例中的input属性均必填
List<Input> inputs = new ArrayList<>();
Input input = new Input();
input.setFromHash("0020b0a75a26caad17b4ea6cec7f059ac0e426d71696a6096f75bb2e9f30c11c60d6");
input.setFromIndex(1);
input.setAddress("Nse5x9foSzFjuwkwZLSvSjAHHLVf3MKJ");
input.setValue(999998760000000L);
inputs.add(input);

//委托共识信息，示例中DepositInfo的属性均必填
DepositInfo info = new DepositInfo();
info.setAddress("Nse5x9foSzFjuwkwZLSvSjAHHLVf3MKJ");            //委托共识的地址
info.setDeposit(300000 * 100000000L);//委托代币数量:2000NULS —— 500000NULS
info.setAgentHash("0020a467827d5f06feb3e78b4603eb03677711219cb5232d145b3e9d4ab48a3eb366");//创建共识节点的交易id

//创建节点的手续费
Na fee = Na.valueOf(1000000L);

Result result = NulsSDKTool.createDepositTransaction(info, inputs, fee);
Map<String, Object> map = (Map<String, Object>) result.getData();
String txHex = (String) map.get("value");
```

------

> **创建委托交易手续费的计算**：手续费单价 \* 交易大小
>
> **手续费单价(min)**：1000000 NA/1KB
>
> **交易大小的计算**：（288 + 50  * inputs.length）/1024 ，
> 其中210为基本信息的固定长度，50为单条input的长度，38为单条output的长度，remark为非必填字段，有需要传入时，按照UTF-8字符编码计算字节长度。交易大小用KB作为单位，最大值为300KB，不足1KB的部分，记为1KB。
> 出块节点在验证每笔交易时，将输入与输出的差值视为用户发送此交易时所支付的手续费，再根据交易的大小计算出手续费的最小值。如果用户的手续费小于最小值，则视为不合法交易，不予打包。因此，在创建交易的时候，手续费的计算应谨慎处理，避免交易失败。
