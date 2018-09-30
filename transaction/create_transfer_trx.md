#### 2.1 创建转账交易
接口

**`Result createTransaction(List<Input> inputs, List<Output> outputs, String remark)`**

说明

> 通过用户传入的交易输入\输出，组装交易。传入的参数为json对象，详见e.g示例。**示例中input和output的属性都为必填项**。交易手续费为inputs和outputs总额的差值，手续费会根据交易大小存在一个最小值，低于最小值时，交易不会被打包。**有关手续费的计算会在后面详细说明**
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
  <td align="center">inputs</td>
  <td align="center">List&lt;Input&gt;</td>
  <td align="center">必填</td>
  <td align="center">交易引用的未花费输出</td>
  </tr>
   <tr>
  <td align="center">outputs</td>
  <td align="center">List&lt;Output&gt;</td>
  <td align="center">必填</td>
  <td align="center">交易新生成的未花费输出</td>
  </tr>
  <tr>
  <td align="center">remark</td>
  <td align="center">String</td>
  <td align="center">非必填</td>
  <td align="center">交易备注</td>
  </tr>
</table>

*e.g 示例代码*

```java
String remark = "create transaction demo";
long fee = 100000;
List<Input> inputs = new ArrayList<>();
List<Output> outputs = new ArrayList<>();

//组装交易的inputs,示例中的input属性均必填
Input input = new Input();
input.setFromHash("002023c66d10cf9047dbcca12aee3db3c921a2ec22e0dd63331cb85");
input.setFromIndex(1);
input.setAddress("2ejPVMKST7h4Qsd5Dqa8Q9Psr47mj5")
input.setValue(1000000000L);      
input.setLockTime(0);
inputs.add(input);

//组装交易的outputs,示例中的output属性均必填
Output output = new Output();
output.setAddress("2CjPVMKST7h4Q5Dqa8Q9P9CwYSmN7mG");
output.setValue(1000000L);
output.setLockTime(0L);
outputs.add(output);

output = new Output();
output.setAddress("2CXJEuoXZMajeTEgL6TgiSxTRRMwiMM");
output.setValue(1000000000L - 1000000 - fee);
output.setLockTime(0L);
outputs.add(output);

Result result = NulsSDKTool.createTransaction(inputs, outputs, remark);
```
---


> **交易手续费的计算**：手续费单价 \* 交易大小
>
> **手续费单价(min)**：100000 NA/1KB
>
> **交易大小的计算**：（124 + 50  * inputs.length + 38 * outputs.length + remark.bytes.length ）/1024
> 124为基本信息的固定长度，50为单条input的长度，38为单条output的长度，remark为非必填字段，有需要传入时，按照UTF-8字符编码计算字节长度。交易大小用KB作为单位，最大值为300KB，不足1KB的部分，记为1KB。
> 出块节点在验证每笔交易时，将输入与输出的差值视为用户发送此交易时所支付的手续费，再根据交易的大小计算出手续费的最小值。如果用户的手续费小于最小值，则视为不合法交易，不予打包。因此，在创建交易的时候，手续费的计算应谨慎处理，避免交易失败。
