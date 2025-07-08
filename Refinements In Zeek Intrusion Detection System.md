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

## 架構
增加四項功能來改善Zeek的使用限制
1. 增加城市與國家名稱
2. 過濾掉特定的domain
3. 過濾掉特定的port
4. 將local與remote的連線放入不同的log檔中!
流程圖如下：

| ![[Process_Flow_of_Refinements_in_Zeek_IDS.png\|425]] |
| ----------------------------------------------------- |
|                                                       |


## 想法

目前準備要看Proposed work，但我覺得這篇好像沒做什麼，架構上看到的只有針對原本的架構新增四項檢查，也沒有什麼performance上的增加，不知道有什麼用。