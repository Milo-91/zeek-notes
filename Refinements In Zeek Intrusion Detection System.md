---
reference: "[[Refinements In Zeek Intrusion Detection System]]"
tags:
  - zeek
read: true
---
## 介紹
利用增加一些features來改善Zeek IDS的logging activities，目的是希望此系統能不經修改直接放置於網路中就可以監聽許多不同的主機。

## Intrusion Detection System (IDS)
[[Intrusion Detection System (IDS)]]

## 比較不同IDS
本篇中比較了三種IDS，分別為Snort、Suricata與Zeek，結論說明Zeek的使用性更高，可以應對更多不同的使用情境。
### Snort
- signature-based IDS
- single-threaded program
- working with Libpcap as its packet-sniffing library

### Suricata
- signature-based IDS
- multi-threaded program
- monitoring network in real-time or analyzing offline packet capture
### Zeek
[[Zeek]]

## 架構
增加四項功能來改善Zeek的使用限制
1. 增加城市與國家名稱
2. 過濾掉特定的domain
3. 過濾掉特定的port
4. 將local與remote的連線放入不同的log檔中!
流程圖如下：

| ![[Process_Flow_of_Refinements_in_Zeek_IDS.png\|575]] |
| ----------------------------------------------------- |
| <center>實作架構流程圖                                       |

## 想法

目前準備要看Proposed work，但我覺得這篇好像沒做什麼，架構上看到的只有針對原本的架構新增四項檢查，也沒有什麼performance上的增加，不知道有什麼用。