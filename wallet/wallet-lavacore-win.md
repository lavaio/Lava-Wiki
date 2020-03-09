## Windows全节点钱包使用教程  
### 步骤一：下载最新版本全节点钱包  
首先下载最新版本的钱包（windows全节点钱包），可前往Lava官网（www.lavatech.org）顶部的下载栏目进行下载：  
![image](https://note.youdao.com/yws/api/personal/file/F650714FFD2A4B64A371A3E6CBCFA667?method=download&shareKey=06062c42731b8dc2e403741dd6e1a7cf)  
### 步骤二：解压缩  
解压下载后的压缩包，解压后有lavad.exe和lava-cli.exe。  
### 步骤三：运行Lavad并完成同步  
在执行文件目录下，按住shift右击打开powershell,如下图：  
![image](https://note.youdao.com/yws/api/personal/file/8761F38645BB45FE8DDD904AB2D500D1?method=download&shareKey=e5358a147e5649849b35ebe56cbf9ad4)  
a.在打开的powershell界面中输入.\lavad -rpcuser=test -rpcpassword=test，然后回车，启动钱包。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/8B53C3263A904D15817F3C860AC7B491?method=download&shareKey=9914d0f71ddcd2388f9ee2f8bb6cd254)  
lavad启动后，请等待程序自动同步至最新块高（最新块高信息可以在区块链浏览器中获得，同步过程可能需要消耗一定时间）。  
### 步骤四：在钱包客户端（lava-cli.exe）内进行钱包操作  
b.在执行目录下打开一个新的powershell（原lavad的窗口保留即可，无需再进行任何操作），输入.\lava-cli -rpcuser=test -rpcpassword=test getblockchaininfo可以查询链当前信息，chain值表示连接的区块链是主网（main）还是测试网（test）；blocks值表示当前已经同步到的区块高度。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/94D33B936DD74919A7E8DAF5A59AA3B0?method=download&shareKey=5f346b56cd3bf93390737d5f0969f497)  
c.如果需要查询帮助（会展示所有可用的命令列表）,输入.\lava-cli -rpcuser=test -rpcpassword=test help。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/677E88CF74FB43FE83C8705E6FB30C0A?method=download&shareKey=3370c3aa50e48da4c22d9ef11941aff0)  
d.生成挖矿地址与Plot ID，输入.\lava-cli -rpcuser=test -rpcpassword=test getmineraddress获取。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/A4B37CF454F64ECEA43BE7261E6051F8?method=download&shareKey=0dc999e913adc04502092545501fcb25)  
e.备份钱包文件 ，输入.\lava-cli -rpcuser=test -rpcpassword=test dumpwallet "filename"。filename为文件名，可以自己另取。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/88C496D3ABFB47B09C2BD60BA513B85C?method=download&shareKey=2a5a9598f77cee88f47b47dfb48f6d81)  
f.导入钱包文件，输入.\lava-cli -rpcuser=test -rpcpassword=test importwallet "filename"。”filename”为前面备份的钱包文件，需要带上路径。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/26A79A36C41D40559F41069EC2788E8A?method=download&shareKey=6f54502d8d82741afc0ed0dc97159c5f)  
g.停止钱包，输入.\lava-cli -rpcuser=test -rpcpassword=test stop。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/9CC13AA3D5694392A8F9A145D1C1AA7C?method=download&shareKey=e58c3ca44276ee68c1c4fd762ad5f977)  
h.导出私钥，输入.\lava-cli -rpcuser=test -rpcpassword=test dumpprivkey "address"。 其中address为钱包地址。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/6997C0484564484A821DA420A6876A5B?method=download&shareKey=62002e9899606a68a841a77ffca88793)  
i.导入私钥 ,输入.\lava-cli -rpcuser=test -rpcpassword=test importprivkey "key" true。 其中key为需要导入的私钥。如下图:  
![image](https://note.youdao.com/yws/api/personal/file/F492BD341BBE4875978B0868C0C669DF?method=download&shareKey=805efa69ce6f2f32b81c99819c0c0b31)  
j.设置交易费，输入.\lava-cli -rpcuser=test -rpcpassword=test settxfee 0.00001。如下图:  
![image](https://note.youdao.com/yws/api/personal/file/08245DE3D56C4948BCD885614A90BFC4?method=download&shareKey=d497b4335b4d69f3cf68be982feb5c40)  
k.查询钱包余额，输入.\lava-cli -rpcuser=test -rpcpassword=test getbalance。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/14C5AE52811C4A94902BBE063AA6C86E?method=download&shareKey=a70e46a1376a95a7b3f1e891369c4516)  
l.绑定算力，输入.\lava-cli -rpcuser=test -rpcpassword=test  bindplotid "fromaddress" "targetaddress"。其中fromaddress为p盘的plotid对应的那个地址，targetaddress为接受出块币奖励的地址。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/C2819B25DA19430B963112CE8B306138?method=download&shareKey=3375b0dca7f36eca7b8c0b10810cd282)  
m.查询绑定关系，输入.\lava-cli -rpcuser=test -rpcpassword=test listbindings 。如下图：  
![image](https://note.youdao.com/yws/api/personal/file/7A6FF41F8B0D444BB9C7BDF1B9CE73F1?method=download&shareKey=0459c29ec867c67ed889a700df70ba02)  
n.解绑算力，输入.\lava-cli -rpcuser=test -rpcpassword=test unbindplotid "address"。如下图:  
![image](https://note.youdao.com/yws/api/personal/file/168CC87E0AB94BBCA745E06B46096011?method=download&shareKey=17cea0bb10bffa63c6825dae751f1e2e)
 

