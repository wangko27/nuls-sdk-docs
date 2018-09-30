#### 2.3 根据交易hash查询交易详情
接口

**`Result getTxByHash(String hash)`**

说明

> 根据交易hash查询交易详情
>
> Result.data <a href="#Transaction">`Transaction`</a>

<table>
    <tr>
        <th align="center">参数</th>
        <th align="center">类型</th>
        <th align="center">是否必填</th>
        <th align="center">说明</th>
    </tr>
    <tr>
        <td align="center">hash</td>
        <td align="center">String</td>
        <td align="center">必填</td>
        <td align="center">交易的hash值</td>
    </tr>
    </table>

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
        "hash": "00203a169b42e5e142e20b273ac925e55f773b5a38c5f5c907efdbc43abb7d7a67b2",
        "type": 2,
        "time": 1529323198461,
        "blockHeight": 1884,
        "fee": 100000,
        "value": 99900000000,
        "remark": "转账",
        "scriptSig": "21036dd27c9fa786a1e83df204e9b31ddc24745c378f1f6b42731d07f05347167c0000473045022100ff3372711d78eb554be331aa40cd7af246641ecd3bc06f2fdca7faefb25f74e50220743a2f2d9d01b5a77a878349b996cbe4953af5d1a946519a5ce4d1129cf99848",
        "status": 1,
        "confirmCount": 14,
        "size": 255,
        "inputs": [
            {
                "fromHash": "0020ab020707282932e6ec701f0b64e22e937fdd03ce9b37aab498aed2e00b6fa8e7",
                "fromIndex": 0,
                "address": "2ChDcC1nvki521xXhYAUzYXt4RLNULS",
                "value": 9999899000000
            }
        ],
        "outputs": [
            {
                "txHash": "00203a169b42e5e142e20b273ac925e55f773b5a38c5f5c907efdbc43abb7d7a67b2",
                "index": 0,
                "address": "2CiVA3n1VoNQobAax4d7qNEBZAfehLN",
                "value": 99900000000,
                "lockTime": 0,
                "status": 0
            },
            {
                "txHash": "00203a169b42e5e142e20b273ac925e55f773b5a38c5f5c907efdbc43abb7d7a67b2",
                "index": 1,
                "address": "2ChDcC1nvki521xXhYAUzYXt4RLNULS",
                "value": 9899998900000,
                "lockTime": 0,
                "status": 0
            }
        ]
    }
}
```
*e.g 示例代码*

```java
getTxByHash("041f3d2ceed........");
```
---
