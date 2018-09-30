#### 3.1 根据区块高度获取区块头
接口

**`Result getblockHeader(int height)`**

说明

> 根据区块高度获取区块头信息
>
> Result.data <a href="#BlockHeader">`BlockHeader `</a>

<table>
    <tr>
        <th align="center">参数</th>
        <th align="center">类型</th>
        <th align="center">是否必填</th>
        <th align="center">说明</th>
    </tr>
    <tr>
        <td align="center">height</td>
        <td align="center">int</td>
        <td align="center">必填</td>
        <td align="center">区块高度</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
        "hash": "002078656b6e32f4f1e9e881e7b6c4c5de036ae81ec5bf78861bde9480f5ff3a1b33",
        "preHash": "0020ee5d28fde669adb0ad16f3ed426f1ee8df40560bed0ab30bb99cbf95df276d64",
        "merkleHash": "0020cc37658e2d110c1d42f64c7fd3dcb56d9653d4edc4d3a8406cb263a41f9f5488",
        "time": 1529299160000,
        "height": 4,
        "txCount": 4,
        "packingAddress": "2CWsZb9w8XXTE58TUhBGczxf4U6NULS",
        "scriptSig": "2102e18d02154e0f68900898efea7ba72d6d14e37d7d173a62146df2871f40996d7300473045022100d4d92a9518ffd855441c7712f4b31bd003291dc108fa2b455fe26d51e54625f102202ae8375bd69bf1928f9967edac82619ff78f30550c17797cc489d5effd3202bf",
        "roundIndex": 419517,
        "consensusMemberCount": 1,
        "roundStartTime": 1529299150000,
        "packingIndexOfRound": 1,
        "confirmCount": 1909,
        "reward": 0,
        "fee": 0,
        "size": 1
    }
}
```
*e.g 示例代码*

```java
getblockHeader(10);
```
