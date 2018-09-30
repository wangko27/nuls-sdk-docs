## 介绍
本文档是NULS Java SDK的用户指南，描述了NULS服务提供的账户、交易、区块等相关基础功能接口的使用说明。
### 约定
- 所有SDK接口统一返回Result(说明见文末附件数据解释)
- 每个接口描述的返回对象是指Result中data属性的内容
- 除特别注明外，本文档NULS都以Na为单位 1NULS = 100,000,000Na
- 运行SDK前，需要确认NULS节点服务已经启动并工作正常
- 推荐使用JDK1.8+

### 版本更新记录



|    版本     |    更新日期    |                   更新内容                   |
| :-------: | :--------: | :--------------------------------------: |
| v0.9.11.0 | 2018-06-19 |            对接NULS服务各项基础功能的接口             |
| v0.9.11.1 | 2018-06-22 |    新增获取最新区块的高度和hash的接口(3.6，3.7)，修改2.1    |
|  v0.9.14  | 2018-07-04 | 修改快速入门中SDK初始化方法改为init，以及SDK的使用方式, 修改返回封装对象名称（去掉Dto等） |
|  v0.9.15  | 2018-07-07 |            新增4个共识接口，4.1——4.4             |
|  v0.9.16  | 2018-07-11 |                 新增接口4.5                  |
|  v1.0.1   | 2018-07-13 |                  新增错误码                   |



## 快速入门
### 1.引入文件
使用构建工具导入jar包  

- maven方式

```xml
<dependency>
   <groupId>io.nuls.sdk</groupId>
   <artifactId>sdk-all</artifactId>
   <version>1.0.1</version>
</dependency>
```

### 2.创建SDK实例
首先添加SDK命名空间

```java
//SDK启动类命名空间
import io.nuls.sdk.SDKBootstrap;
import io.nuls.sdk.model.Result;
//引入SDK调用工具的命名空间
import io.nuls.sdk.tool.NulsSDKTool;
```

引入后 使用下列代码生成一个实例client    

- 初始化SDK
- 初始化方法不传参数时，默认PRC ip和端口分别为`127.0.0.1`，`8001`

```java
//默认
SDKBootstrap.init();
//传入NULS服务的ip，port
SDKBootstrap.init("192.168.1.88", "8001");
```

- 使用工具类调用接口方法


```java
Result result = NulsSDKTool.createAccount("nuls123456");
```
 *e.g 创建一个带密码的账户的完整示例*

```java
import io.nuls.sdk.SDKBootstrap;
import io.nuls.sdk.model.Result;
//根据需求引入对应模块的命名空间
import io.nuls.sdk.tool.NulsSDKTool;

public static void main(String[] args) {
	SDKBootstrap.init();
	Result result = NulsSDKTool.createAccount("nuls123456");
}
```
