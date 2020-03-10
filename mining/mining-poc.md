# 了解PoC共识

## 简单了解PoC共识

PoC是**Proof-of-Capacity**的简写，中文直译为**“容量证明”**，亦有称为“空间证明”或“空间容量证明”。

PoC 是一种基于存储空间的共识机制，锻造人（矿工）通过提供更大的存储空间容量来提高制造区块的成功率。

PoC 锻造人依赖于静态存储的特殊数据参与锻造区块的竞争。这些特殊数据是按照特定哈希算法得到的一系列有序计算结果的阵列，由锻造人预先通过计算生成、并通过密码学手段绑定在锻造人地址下。由此方式处理完成的数据被称为**Plot 文件**。

锻造过程中，共识机制通过待产出区块的数据，随机性指定 Plot 文件数据阵列中的特定位置。参与锻造的竞争者检索自身 Plot 文件中的对应数据，生成一个 Deadline；Deadline 表示节点可广 播新区块前等待时间，因此产生最小 Deadline 意味着锻造成功。考虑到 Plot 文件可以一次生成、长期保存并重复使用，而锻造过程所需要的工作仅限于网络广 播、检索以及简单的验证性计算，因此 PoC 机制对高性能计算资源以及电力能源的消耗可以被降到最低限度。在同等安全条件下，PoC 运行所需的电力消耗仅为 PoW 机制的数百分之一数量级。

## 历史沿革

开源项目**Burst**是较早研究并实践PoC共识的数字加密货币，可被认为是PoC共识之先驱者。

PoC共识中所涉及的诸多重要机制与算法，通过Burst等项目提出或完善，并逐渐形成现存通行的算法。PoC共识中的诸多核心概念，如Plot过程、PoC2算法、Deadline、GenSig等，都来源于这些先驱者的构思、验证与总结。

Lava在充分吸收已有项目所展现的智慧与经验之基础上，结合最为稳定的比特币Codebase连同UTXO机制，又开创并实践了Lava特有的火石机制。Lava将长期愿景定位于“追求更加去中心化的数字加密货币”以及“成为全球存储空间的信任之根”，势必成为不可或缺的区块链基础设施。

## 了解更多…

* **Lava白皮书**详细阐释了PoC共识的基本原理与过程：

    <https://www.lavatech.org/pdf>

* BurstWiki对PoC概念的解释：

    <https://burstwiki.org/en/proof-of-capacity/>

* Busrtcoinist对PoC共识过程与优点的总结：

    <https://burstcoin.ist/2017/10/16/the-burst-mining-process-explained/>

* Lava社区为小白解读PoC原理：

    <https://www.8btc.com/article/472229>

* Lava社区对比PoC与PoW之优劣：

    <https://www.8btc.com/article/475470>

* Lava社区提供关于PoC与硬盘挖矿概念的辨析：

    <https://www.8btc.com/article/478136>



