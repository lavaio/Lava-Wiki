# 购买与释放火石

## 向系统抵押LV获得火石（即购买火石）：

```text
.\lava-cli.exe -rpcuser=test -rpcpassword=test buyfirestone "购买火石的地址" "指定找零地址"
```

成功执行返回交易ID。

需要注意，火石是关联到地址的。例如，您通过该命令给地址A购买了火石，未来只有地址A的私钥能够使用火石以及释放火石。

一般情况下，给挖矿地址购买火石即可，这样当您的挖矿地址出块时，火石也会被自动使用以获得双倍Coinbase收益。

此外，buyfirestone命令目仅支持向`P2PKH`地址（Pay2PubkeyHash地址，主网1开头地址）购买火石，不支持向`P2SH`地址（隔离见证地址，主网3开头地址）购买火石。

找零地址是指购买火石交易引用了可用的TX Input余额后，向用户返回多余资金时接受找零资金的地址。

## 查询当前周期（Slot）信息：

```text
.\lava-cli.exe -rpcuser=test -rpcpassword=test getslotinfo
```

返回结果如下：

```text
{
  "index": 5,
  "price": 16716105000,
  "count": 10,
  "locktime": 767
}
```

说明：

`index`表示现在处于第几个周期（Slot），周期从0开始计，即第一个周期的index=0。

`ticketprice`表示当前火石的价格，需要注意该价格是以satoshi为单位，除以100000000得到以LV计的价格。

`ticketcount`表示当前全网已经购买的火石数量。

`locktime`表示在当前周期购买火石的成熟块高，达到这个块高以后才可以使用现在购买的火石。

## 查询地址持有火石情况：

```text
.\lava-cli.exe -rpcuser=test -rpcpassword=test getfirestone “你要查询的地址”
```

返回结果如下：

```text
[
  {
    "outpoint": "615fb809eb973667ea8523ecf11bf93eafdf7924521bc172abb09329d141a3e8:1",
    "address": "n4CpQvwua2NXnoq7rJbp41JzbcvUGDL1f1",
    "lockheight": 511,
    "state": "IMMATURATE",
    "isSpent": false
  }
]
```

说明：

`outpoint`表示购买火石的交易ID，即当时购买该火石所发起的交易记录。

`address`表示火石所关联的地址。

`lockheight`表示该火石在这个块高以后为可用状态。

`state`表示火石的状态，`IMMATURATE`表示还未成熟（请等待下一个周期成熟），`USABLE`表示现在可用，`OVERDUE`表示已经过期。

`isSpent`表示火石是否被使用。false表示未被使用。

## 释放过期的火石

如果火石在出块的时候消耗掉了，就不需要手动释放；如果没有被消耗掉，需要在过期后手动释放。

```text
.\lava-cli.exe -rpcuser=test -rpcpassword=test freefirestone "持有火石的地址" "接受释放资金的地址"
```

成功释放后返回交易ID。

如果您希望抵押的资金释放回原先持有火石的地址，两个地址填一样的即可。

