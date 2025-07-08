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
這篇論文出自ICACCS，主辦國家在印度，提出者為印度GLA University的學生或研究人員不清楚，但以email的格式感覺是大學或碩士生。看下來感覺不是一篇很好的論文，全部內容只有五頁，裡面講述提出架構的部分只佔一到兩頁，前面只是在介紹與提倡Zeek這個Program的優勢，架構的部分沒有寫出改良的Performance差異與原因，只是單純修改了原本程式中的功能，在過濾特定domain與特定port的部分也不知道為什麼要濾掉這些部分，感覺只是單純在展現功能，圖片也是直接左右壓縮沒有在管閱讀性。看完沒有多獲得什麼。