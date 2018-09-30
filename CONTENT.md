### 附录

#### 接口返回Result示例
##### Result

- 表示接口访问正常，业务返回具体的数据

```json
{
    "success": true,//接口执行的正确性
    "data": data
}
```
- 表示接口访问正常，业务返回true

```json
{	//表示接口访问正常，业务返回true
    "success": true,//接口执行的正确性
    "data": {
		"value":true //接口业务功能的返回结果
    }
}
```
- 表示接口访问正常，业务返回false

```json
{
    "success": true, //接口执行的正确性
     "data"：{
        "value": false //接口业务功能的返回结果
     }
}
```
- 返回错误的情况,例如参数错误，异常等

```json
{	//表示错误的情况
    "success": false,
     "data"：{
        "code": "ACT005",
        "msg": "xxxxxx...."
     }
}
```

- 这是创建一个带密码的离线账户的完整返回结果

```json
{
    "success": true,
    //data为List<account>
    "data": {
    	"list":[
        	{
	           "address": "2CacFwqMwcJiGNNBwiwV7bCL7bjwNBr",
	            "alias": null,
	            "pubKey": "030d4e752b5aa5d784f19a1fcc73b02afb6f756752fd00ebc2fcaabc8d0979c4f0",
	            "extend": null,
	            "createTime": 1529041525794,
	            "encrypted": false,
	            "priKey": "00e4bfd347351ea899b5f0ae2c0a3e7a6951b202eaf72432d1a63a2dc85c59c82a",
	            "encryptedPriKey": ""
	    	}
	    ]
    }
}
```
---

##### <a name="Account"> Account </a>
```json
{
	"address": String, 账户地址
	"alias": String, 账户别名
	"pubKey": String, 公钥
	"extend": String, 扩展
	"createTime": Long, 创建时间
	"encrypted": boolean, 是否加密
	"priKey": String, 私钥（创建无密码离线账户时才会有值）
	"encryptedPriKey": String, 加密私钥（创建有密码离线账户时才会有值）
}
```
---

##### <a name="Input"> Input </a>
```json
 {
	"fromHash": String, 来源output的txHash         
	"fromIndex": Integer, 来源output的outIndex
	"address": String, 转入地址                   
	"value": Long 转入金额
    "lockTime": Long 锁定时间
}
```
---

##### <a name="Output"> Output </a>
```json
 {
	"txHash": String, 交易hash
	"index": Integer, 索引
	"address": String, 地址
	"value": Long, 数量
	"lockTime": Long, 锁定时间
	"status": Integer 状态 0:usable(未花费), 1:timeLock(高度锁定), 2:consensusLock(参与共识锁定), 3:spent(已花费)
}
```
---

##### <a name="Transaction"> Transaction </a>

```json
{
	"hash": String, 交易的hash值
	"type": Integer, 交易类型
	"time": Long, 交易发起时间
	"blockHeight": Long, 区块高度
	"fee": Long, 交易手续费
	"value": Long, 交易金额
	"remark": String, 备注
	"scriptSig": String, 签名
	"status": Integer, 交易状态 0:unConfirm(待确认), 1:confirm(已确认)
	"confirmCount": Long, 确认次数
	"size": int, 大小
	"inputs": [
		{
			"fromHash": String, 来源output的txHash
			"fromIndex": Integer, 来源output的outIndex
			"address": String, 转入地址
			"value": Long 转入金额
		}
		],
	"outputs": [
		{
			"txHash": String, 交易hash
			"index": Integer, 索引
			"address": String, 地址
			"value": Long, 数量
			"lockTime": Long, 锁定时间
			"status": Integer 状态 0:usable(未花费), 1:timeLock(高度锁定), 2:consensusLock(参与共识锁定), 3:spent(已花费)
		}
	]
}
```
---

##### <a name="BalanceInfo"> BalanceInfo </a>
```json
{
	"balance": long, 余额
	"usable": long, 可用余额
	locked": long 锁定余额
}
```
---

##### <a name="BlockHeader"> BlockHeader</a>

```json
{
	"hash": String, 区块的hash值
	"preHash": String, 上一个区块的hash值
	"merkleHash": String, 梅克尔hash
	"time": Long, 区块生成时间
	"height": Long, 区块高度
	"txCount": Long, 区块打包交易数量
	"packingAddress": String, 打包地址
	"scriptSig": String, 签名
	"roundIndex": Long, 共识轮次
	"consensusMemberCount": Integer, 参与共识成员数量
	"roundStartTime": Long, 当前共识轮开始时间
	"packingIndexOfRound": Integer, 当前轮次打包出块的名次
	"confirmCount": Long, 确认次数
	"reward": Long, 共识奖励
	"fee": Long, 获取的打包手续费
	"size": int, 大小
}
```
---

##### <a name="Block"> Block</a>

```json
{
	"hash": String, 区块的hash值
	"preHash": String, 上一个区块的hash值
	"merkleHash": String, 梅克尔hash
	"time": Long, 区块生成时间
	"height": Long, 区块高度
	"txCount": Long, 区块打包交易数量
	"packingAddress": String, 打包地址
	"scriptSig": String, 签名
	"roundIndex": Long, 共识轮次
	"consensusMemberCount": Integer, 参与共识成员数量
	"roundStartTime": Long, 当前共识轮开始时间
	"packingIndexOfRound": Integer, 当前轮次打包出块的名次
	"confirmCount": Long, 确认次数
	"reward": Long, 共识奖励
	"fee": Long, 获取的打包手续费
	"size": int, 大小
	"txList": [
		{
			"hash": String, 交易的hash值
			"type": Integer, 交易类型
			"time": Long, 交易发起时间
			"blockHeight": Long, 区块高度
			"fee": Long, 交易手续费
			"value": Long, 交易金额
			"remark": String, 备注
			"scriptSig": String, 签名
			"status": Integer, 交易状态 0:unConfirm(待确认), 1:confirm(已确认)
			"confirmCount": Long, 确认次数
			"size": int, 大小
			"inputs": [ 输入
				{
					"fromHash": String, 来源output的txHash
					"fromIndex": Integer, 来源output的outIndex
					"address": String, 转入地址
					"value": Long 转入金额
				}
			],
			"outputs": [ 输出
				{
					"address": String, 地址
					"value": Long, 数量
					"lockTime": Long, 锁定时间
				}
			]
		}
	]
}
```
---

#### 错误码

```
("SYS000", "10000") SUCCESS
("SYS001", "10001") FAILED
("SYS006", "10006") DATA_ERROR       
("SYS018", "10018") PARAMETER_ERROR     
("SYS021", "20021") SIGNATURE_ERROR        
("DATA004", "11000") VERIFICATION_FAILD  
("DATA001", "11001") DATA_PARSE_ERROR        
("ACT000", "50000") PASSWORD_IS_WRONG        
("ACT001", "50001") ACCOUNT_NOT_EXIST        
("ACT002", "50002")ACCOUNT_IS_ALREADY_ENCRYPTED
("ACT003", "50003")ACCOUNT_EXIST        
("ACT004", "50004")ADDRESS_ERROR         
("ACT005", "50005") ALIAS_EXIST        
("ACT006", "50006")ALIAS_NOT_EXIST         
("ACT007", "50007") ACCOUNT_ALREADY_SET_ALIAS       
("ACT008", "50008")PARAMETER_ERROR        
("ACT009", "50009") DATA_PARSE_ERROR        
("ACT010", "50010")SUCCESS         
("ACT011", "50011") FAILED        
("ACT012", "50012")INSUFFICIENT_BALANCE   
("ACT013", "50013") ALIAS_ROLLBACK_ERROR      
("ACT014", "50014") ACCOUNTKEYSTORE_FILE_NOT_EXIST      
("ACT015", "50015") ACCOUNTKEYSTORE_FILE_DAMAGED       
("ACT016", "50016") ALIAS_FORMAT_WRONG      
("ACT017", "50017")PASSWORD_FORMAT_WRONG

("LED001", "12001");UTXO is unable
("LED002", "12002");UTXO status error
("LED003", "12003");Lack of balance
("LED004", "12004");Invalid input
("LED005", "12005");Invalid input
("LED006", "12006");Orphan transaction
("LED007", "12007");Orphan block
("LED008", "12008");Data not found
("LED009", "12009");Tx fee is not right
("LED0010", "120010");Rollback Transaction tx failed
("LED0011", "120011");Transaction repeated
("LED0012", "120012");The amount of the transfer is too small
("LED0013", "120013");The transaction is too big

("LEDGER002", "69981");Repeated transactions
```
