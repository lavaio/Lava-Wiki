# CA资产发行教程
## 1.概念介绍  
Confidential Asset（简称CA）方案是在Confidential Transaction方案基础上改造和拓展而来，可实现在链上发行并交易Multi-asset，且完美隐藏资产类型信息和交易金额。  
## 2.安装Windows版本钱包  
到官网（https://www.lavatech.org/zh/download） 下载CA测试网全节点钱包，安装全节点钱包至少需要 10 GB 磁盘空间。本教程以testnet-lava-win64-v0.4.4为示例：  
### 2.1 下载并解压Lava Core （CA测试网全节点钱包）  
![image](https://note.youdao.com/yws/api/personal/file/C0A94E21BC7C43E5B758068A733A5E80?method=download&shareKey=7f52255481208b53ff46a4f1c3cc0552)  
### 2.2 以测试网模式启动全节点钱包  
![image](https://note.youdao.com/yws/api/personal/file/F50DB7B19D5A49DBB536870E07FA49A5?method=download&shareKey=50fc1c939f944bdbace48cd81900b241)  
### 3. CA资产发行  
**API**：issueasset  
**调用参数**：  
assetamount：要生成的资产数量  
tokenamount：在发行通证数量  
blind：是否盲化发行数量，默认值：true  
![image](https://note.youdao.com/yws/api/personal/file/E2D710FAD5EF4D1FAF36465C7FBA2754?method=download&shareKey=3d39f5263c3bd3a5f80b11d9d7c242f6)  
**注意事项**：这个调用需要消耗一个钱包中的LAVAUTXO，并将全额返还到钱包的一个 新地址，以便确保发行是唯一的，但是这也意味着你的钱包中至少需要有0.00000001 个LAVA才能执行issueasset调用  
### 4. CA资产增发  
**API:** reissueasset  
**调用参数：**  
Asset：要再次发行的资产ID，字符串  
Amount：要创建的额外资产数量，数值  
![image](https://note.youdao.com/yws/api/personal/file/CBEF4E00242844B29DE17E44BF7E2142?method=download&shareKey=7c5aff57e6831efda82d3f6ae608251e)  
**注意事项**：必须在钱包中持有在发行通证才可以操作再发行，但是在此过程中不会消耗再发行通证总量。  
### 5. CA资产销毁  
**API**: destroyamount  
**调用参数：**  
asset：资产标识字符串  
amount：要销毁的资产数量  
comment：备注信息，该备注不进交易  
![image](https://note.youdao.com/yws/api/personal/file/6AAB440B35BA4D2EAADDED7992C30B40?method=download&shareKey=c19748ba1ebf88e981e03cb0ffa117ef)  
**注意事项**：钱包中必须包含至少该数量的资产以用于销毁。  
### 6. 生成隐私地址  
**API**: getnewaddress  
**调用参数**:  
labal  要链接到的地址的标签名称。也可以将其设置为空字符串 “”  
address_type  要使用的地址类型。选项有“legacy”、“p2sh-segwit”和“bech32”  
![image](https://note.youdao.com/yws/api/personal/file/5E898D94B36C48719D299DD391CDCE90?method=download&shareKey=497980723b8ceeb096a046e52ef7b3c9)  
### 7. 发送CA资产  
**API**: sendtoaddress  
**调用参数**：  
ToAddress：目标地址，字符串  
Amount：发送数量，数值  
Comment：备注信息，字符串，可选  
CommnetTo：备注to，字符串，可选  
SubtractFeeFromAmount：是否从发送金额中扣除手续费，布尔值，可选，默认值：false  
Replaceable：允许此交易通过BIP 125被更高费用的交易所取代.,可选  
Conf_target：可选，默认=回退到钱包默认值 确认目标(块)  
estimate_mode：费用估计模式，可选，默认=UNSET  
Assetlabel：十六进制资产id或资产标签余额，可选  
Ignoreblindfail：即使交易失败也返回一个事务，可选，默认=true  
![image](https://note.youdao.com/yws/api/personal/file/8C60897038D74DF58A93D77D98A3DBE3?method=download&shareKey=7fd775c610a8bd55d6813575a39f431f)  
### 8. 查看账户余额  
**API**: getbalance  
**调用参数**：  
dummy：(字符串，可选)保留向后兼容性。必须排除或设置为“*”  
minconf：可选值，默认=0  
include_watchonly：可选值，默认=false  
assetlabel：资产标识符，可选   
![image](https://note.youdao.com/yws/api/personal/file/ADC383840B1B4CFAB5CFFBF1EE35E08B?method=download&shareKey=337ff03de5f136dbeb851672b8b7f606)  
### 9. 查询资产发行记录  
**API**: listissuances  
**调用参数**：  
asset：要查询的资产的16进制ID  
![image](https://note.youdao.com/yws/api/personal/file/8A386231E5DB4EF2AB0F61BC88D26233?method=download&shareKey=d1f2a965014a17a5edc6263efe5e7ec7)
