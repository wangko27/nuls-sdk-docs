#### 4.5 获取委托共识列表

接口

**` Result getDeposits(String address, int pageNumber, int pageSize) `**

说明

> 获取地址的委托共识列表
>
> Result.data List委托列表信息

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
<td align="center">委托地址</td>
</tr>
<tr>
<td align="center">pageNumber</td>
<td align="center">Int</td>
<td align="center">必填</td>
<td align="center">页码</td>
</tr>
<tr>
<td align="center">pageSize</td>
<td align="center">Int</td>
<td align="center">必填</td>
<td align="center">每页显示条数，1-100之间</td>
</tr>
</table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
  "success":true,
  "data":{
    "pageNumber":1,
    "pageSize":10,
    "total":1,
    "pages":1,
      "list":[
        {
        "deposit":20000010000000,
        "agentHash":"00207654b3371e9c99295a4b3d0371a6cfec48ee31684825dabc04dc5ea314da0a0c",
        "address":"NsdyD94pXWpxZudbtJ4zpkBHhh8XmBQA",
        "txHash":"002029411a2e6797e2d3bec54c48008f73275c8208a240b4835be534a137452bc29e",
        "blockHeight":98,
        "agentAddress":"NsdyD94pXWpxZudbtJ4zpkBHhh8XmBQA"
        }
      ]
  }
}
```

*e.g 示例代码*

```java
Result result = NulsSDKTool.getDeposits(address, 1, 10);
```
