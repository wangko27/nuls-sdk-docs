#### 3.3 根据区块高度获取区块
接口

**`Result getBlock(int height)`**

说明

> 根据区块高度获取区块
>
> Result.data <a href="#Block">`Block `</a>

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
        "hash": "00209bbcd98110b57f1ecd66c9d94d1a2381e6c03c3b9aa77db25b6eb5955bb658d3",
        "preHash": "00201c0fa53c98595c7f9ba817fca6367aa2da1c1e480f801766b7a4a16b39c54b67",
        "merkleHash": "00200c2dfa0560229ef728cd6bdc858334ef4072d8e25c3b0831c8366f4d4cb0c168",
        "time": 1529323210000,
        "height": 1884,
        "txCount": 1884,
        "packingAddress": "2CWsZb9w8XXTE58TUhBGczxf4U6NULS",
        "scriptSig": "2102e18d02154e0f68900898efea7ba72d6d14e37d7d173a62146df2871f40996d73004730450221009d1015b7cab19ac8099245390ae41ca14da9f47d5c28b3b7780a53bd8adcccd802202bf74bb764f9de248dfb892d98e9ff91bad25daa107cfdf4effd3fb1c266e5ae",
        "roundIndex": 420416,
        "consensusMemberCount": 5,
        "roundStartTime": 1529323170000,
        "packingIndexOfRound": 4,
        "confirmCount": 33,
        "reward": 100000,
        "fee": 100000,
        "size": 5,
        "txList": [
            {
                "hash": "00202b9737b15bf7e4ebc74a58554e461fbed6fedf3e289c6ef41afa80d83f67babc",
                "type": 1,
                "time": 1529323210000,
                "blockHeight": 1884,
                "fee": 0,
                "value": 0,
                "remark": null,
                "scriptSig": null,
                "status": 0,
                "confirmCount": 33,
                "size": 54,
                "inputs": [],
                "outputs": [
                    {
                        "address": "2CWsZb9w8XXTE58TUhBGczxf4U6NULS",
                        "value": 100000,
                        "lockTime": 2884
                    }
                ]
            },
            {
                "hash": "00203a169b42e5e142e20b273ac925e55f773b5a38c5f5c907efdbc43abb7d7a67b2",
                "type": 2,
                "time": 1529323198461,
                "blockHeight": 1884,
                "fee": 100000,
                "value": 0,
                "remark": "转账",
                "scriptSig": "21036dd27c9fa786a1e83df204e9b31ddc24745c378f1f6b42731d07f05347167c0000473045022100ff3372711d78eb554be331aa40cd7af246641ecd3bc06f2fdca7faefb25f74e50220743a2f2d9d01b5a77a878349b996cbe4953af5d1a946519a5ce4d1129cf99848",
                "status": 0,
                "confirmCount": 33,
                "size": 255,
                "inputs": [
                    {
                        "fromHash": "0020ab020707282932e6ec701f0b64e22e937fdd03ce9b37aab498aed2e00b6fa8e7",
                        "fromIndex": 0,
                        "address": null,
                        "value": 9999899000000
                    }
                ],
                "outputs": [
                    {
                        "address": "2CiVA3n1VoNQobAax4d7qNEBZAfehLN",
                        "value": 99900000000,
                        "lockTime": 0
                    },
                    {
                        "address": "2ChDcC1nvki521xXhYAUzYXt4RLNULS",
                        "value": 9899998900000,
                        "lockTime": 0
                    }
                ]
            },
            {
                "hash": "002040370fcb2ad080abdcd2d91f952826c8f6e55bda7231c1c15f25d9d74dc8ad7f",
                "type": 7,
                "time": 1529323210000,
                "blockHeight": 1884,
                "fee": 0,
                "value": 0,
                "remark": null,
                "scriptSig": null,
                "status": 0,
                "confirmCount": 33,
                "size": 38,
                "inputs": [],
                "outputs": []
            }
        ]
    }
}
```
*e.g 示例代码*

```java
getBlock(10);
```
