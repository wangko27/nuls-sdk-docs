#### 3.6 获取最新区块的高度
接口

**`Result getNewestBlockHight()`**

说明

> 获取最新区块的高度
>
> Result.data 高度(Long)

返回结果  

- 返回结果为`Result`对象，格式如下：

```json
{
    "success": true,
    "data": {
        "value": 5210
    }
}}

```
*e.g 示例代码*

```java
getNewestBlockHight();
```
