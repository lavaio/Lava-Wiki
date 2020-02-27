# 发起与解除算力绑定

## 发起绑定

```text
.\lava-cli.exe -rpcuser=test -rpcpassword=test bindplotid "发起绑定地址" "接受绑定地址"
```

例如矿工甲（持有挖矿地址A）可以发起算力绑定到矿工乙（持有挖矿地址B）。绑定后，甲、乙都可正常挖矿。

当甲的`Plot ID`出块时，对应的`Coinbase`奖励会发到乙的地址B。

绑定成功后，程序会返回绑定交易的ID。

## 查询绑定情况

```text
.\lava-cli.exe -rpcuser=test -rpcpassword=test listbindings
```

查询后程序会展示全网目前的绑定关系。

例如：

```text
[
  {
    "from": {
      "address": "nfmJmsGPgoJGPYsDj4Z5CfpWUQQHHD",
      "plotid": 41940084074803714
    },
    "to": {
      "address": "n2sGZMd2K38SS4yPwEL7NDTJ3pvST6G",
      "plotid": 862315404337908960
    }
]
```

from项表示发起绑定人的信息（包括地址与`Plot ID`）、to项表示接受绑定人的信息（`Plot ID`）。

## 解除已有的绑定关系

```text
.\lava-cli.exe -rpcuser=test -rpcpassword=test unbindplotid "自己的地址"
```

执行此命令后，节点即会向全网广播解除绑定动作的交易，程序会返回该解绑交易的交易ID；待该交易被打包入块上链后，解除绑定动作正式生效。

