## 概念介绍  
“P盘”是Plotting的俗称，指生成Plot文件并填入硬盘的过程。Plot文件是Poc挖矿所必须的基础数据，矿工的硬盘空余容量越大，即可填入更多Plot文件，增加成功出块的概率。如果您想参与Lava挖矿，必须在挖矿前使用由LAVA自行研发的P盘软件HyperPlotter预先完成P盘工作。
## 步骤一：获取publickeyid 
首先，您需要更新全节点钱包至v0.4.1版本（包括lavad和lava-cli）。在新版本全节点中，使用getmineraddress命令获取您的pubkeyid。pubkeyid是使用您的私钥生成的唯一身份辨识符，用以代替旧标准中的Plot ID:  
![image](https://note.youdao.com/yws/api/personal/file/B61E0DAFAC4D4256A184835DBC5ED789?method=download&shareKey=55a680529000a7117f8554781df313c7) 

## 步骤二：下载p盘软件  
HyperPlotter现已上线LAVA官网，其中包含 2个版本的HyperPlotter，版本v0.1.2适用于PoC2协议P盘，版本v0.2.2适用于PoC2+协议P盘。下载地址：https://www.lavatech.org/zh/poc2Upgrade  
## 步骤三：启动p盘软件  
### 每台p盘机器运行一份P盘软件  
1.解压 HyperPlotter-x64-all.zip，进入poc2+v0.2.2文件夹。  
2.参数配置，右击runplotter.bat，选择编辑，如下：  
![image](https://note.youdao.com/yws/api/personal/file/20C5002717D14990804D23B662A00253?method=download&shareKey=d36777d3ed54c4e9142d6af3936a785e)  

![image](https://note.youdao.com/yws/api/personal/file/2B6DC4CAEA2B4F2F9FA6F93E474672C8?method=download&shareKey=77328fa15200cf3eeb52bd91a7cb4cf0)  
3.配置好后，运行p盘软件：  
![image](https://note.youdao.com/yws/api/personal/file/FA4D97320BB64B6DA7C0F9691AAF896E?method=download&shareKey=dad6382de37bd42565592fafefe84731)  
4.p盘完成后会显示如下图所示界面，如果没出现表示P盘任务未完成，重新执行第3步:  
![image](https://note.youdao.com/yws/api/personal/file/BDF759FD6CCE471FB25F185BD114231A?method=download&shareKey=b1fdda7717f55376b96a4233ed0de6d2)  
### 多实例运行  
1.解压HyperPlotter-x64-all.zip，进入poc2+v0.2.2文件夹。  
2.参数配置，复制runplotter.bat多份，并重命名，每个P盘任务一个文件，如下配置了两个P盘任务：  
![image](https://note.youdao.com/yws/api/personal/file/AC336B05E1BC4607B6947B82E93F7720?method=download&shareKey=294e43494696c161d08dbbcba9b43b38)  
3.分别编辑两个文件的参数，注意：硬盘列表不要有重复，内存均匀分配，保证系统有足够的空闲内存可以使用:  
![image](https://note.youdao.com/yws/api/personal/file/CCC163EC2C8648758D9C4D17EA40361E?method=download&shareKey=162993247a06e22732e20a02febb7acd)  

![image](https://note.youdao.com/yws/api/personal/file/56DAA64714A44706A77525AA00A28013?method=download&shareKey=0ac23fd987f1755fd7fb3e7ea6181a84)  
4.分别运行p盘任务：  
![image](https://note.youdao.com/yws/api/personal/file/8D350B38DE74455A824484CDAD09DA55?method=download&shareKey=0d43b8ee55d9eda578fe5a1758ab431e)  
5.P盘完成后会显示如下图所示界面，如果没出现表示P盘任务未完成，重新执行第4步：  
![image](https://note.youdao.com/yws/api/personal/file/18BF44F51CA84B96BF155864AE08F401?method=download&shareKey=8603cf7338f341037ea22b9ffbf4e018)  
### 以管理员身份运行  
1.右击runplotter.bat，选择以管理员方式运行。  
2.右击 runplotter.bat，选择创建快捷方式，创建启动脚本的快捷方式，右击刚创建的快捷方式：  
![image](https://note.youdao.com/yws/api/personal/file/8F825F2933ED4C29B1453E19ACDBB2A3?method=download&shareKey=39f529a71fc92f135d3059a75b0a350f)  
3.打开属性窗口，如下，单击高级按钮:  
![image](https://note.youdao.com/yws/api/personal/file/17ED5FB4F35C4D9E9A0E7C5BC726991E?method=download&shareKey=3b2323999dccc00656216785c311dd3f)  
4.打开高级属性设置，如下钩选用管理员身份运行:  
![image](https://note.youdao.com/yws/api/personal/file/02BFF5BBD59846DDB44FA2CB165F2F8D?method=download&shareKey=26992029a010a23a76bee2928b1982b3)  
最后确定，完成设置，后面即可以直接双击快捷方式来运行P盘任务；每个脚本单独按上面的步骤设置快捷方式即可。

