```
********************************************************************
* __  __                  ___        _                 _____       *
*|  \/  | __ _  ___ _ __ / _ \ _ __ | |__   __ _  __ _|___ /  Tr0y *
*| |\/| |/ _` |/ __| '__| | | | '_ \| '_ \ / _` |/ _` | |_ \       *
*| |  | | (_| | (__| |  | |_| | |_) | | | | (_| | (_| |___) | v1.0 *
*|_|  |_|\__,_|\___|_|   \___/| .__/|_| |_|\__,_|\__, |____/       *
*                             |_|                |___/      Sniffer*
********************************************************************
```
# 中文

## 介绍

有一天我在无意中发现，学校的WLAN是开放的。

也就是说，身边充满了Cookie与明文密码，我们只需要伸伸手，便可以拿到。

然后又发现了add在freebuf发的一篇文章，进而对写一个嗅探器愈发有兴趣，于是就有了这个工具。

## 食用方法

大体上，嗅探器是一个类，有以下参数：

1. iface：可选参数；无线网卡名，若不填则代码会自动指定无线网卡
2. newiface：可选参数；默认值为‘mon0’；由于嗅探需要开启无线网卡的监听模式（monitor），这个是处于监听模式下网卡的名字。
3. filename：可选参数；默认为空；嗅探器可以实时嗅探，也可以解析本地的pcap包，这个参数就是本地pcaps包的名字，注意一定要放在Pcaps目录里；只需填写文件名；
4. outputmode：可选参数；默认为1；嗅探器一旦发现cookie或者post的包，就会进行对应的输出，若不想看见实时输出，则置0，否则置1。
5. savingPkt：可选参数；默认为1；嗅探器发现符合filter的数据时，会对输出的结果进行保存；若不想保存这些结果，置0；默认保存在Pkts下
6. savingPcap：可选参数；默认为0；嗅探器可以保存符合filter的原始数据包；1为保存；0为不保存；默认保存在Pcaps下
7. filtermode：可选参数；默认为空；与scapy的过滤语法一致，对数据包进行过滤；代码在后面默认过滤自己的ip，以及只嗅探web相关的包；
8. iHost：可选参数；默认为空列表；在这里面包含的host，在停止嗅探后会高亮显示。

举个例子：

```
iHost = ['www.baidu.com']
Sniffer(savingPkt = 1, savingPcap = 1, iHost = iHost)
```





## 一些话

目前写的比较粗糙，所以不仅代码奇丑无比，实现也是简单粗暴，后续有时间会改进

 # English

## Introduction

