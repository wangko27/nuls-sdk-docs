#### 3.7 获取最新区块的块Hash
接口

**`Result getNewestBlockHash()`**

说明

> 获取最新区块的块Hash
>
> Result.data Hash值(String)

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
        "value": "0020a2e1c99951184700927472c431a5a65847c7974cac0bbb97b242c7adf56ad27b"
    }
}}

```
*e.g 示例代码*

```java
getNewestBlockHash();
```
