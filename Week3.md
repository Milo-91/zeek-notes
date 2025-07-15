---
tags:
  - 週進度
---
## 週進度

## meeting 內容
### Zeek Scripts
希望可以使用腳本來找出特定攻擊，但目前有查到的腳本很少針對所有類別的攻擊進行偵測，大多都是針對某一種行為進行偵測。
Zeek 跟 netflow 不一樣的部分是有 payload 可以看，所以可以獲得更多資訊，應該要可以偵測出更多的攻擊，但以目前找到的腳本而言，沒辦法建立出一個完整的偵測系統。
我原本預期的是可以找到其他研究團隊所開發的一套 scripts 能讓 Zeek 能偵測出許多不同的攻擊行為，因為我覺得自己撰寫腳本的成本過高而且也不是專業人士，所做出的結果一定有很多缺陷，如果希望未來可以實際使用，使用其他研究團隊所建立出來的結果比較有公信力。
#### 1. Zeek 內建腳本
Zeek 中針對攻擊內建的腳本不多，目前有找到針對異常行為進行檢查的有
1. sql injection
2. ssh / ftp brute force
3. validate certs
4. dns external names: 域名是外部網路，但解析內部網路 IP 位址。
5. email check: 查看信件的寄送國家與網站，與 blacklist 比對。
#### 2. Zeek Packages
在 Github 或是 Zeek 論壇上也沒有找到較全面針對攻擊進行辨識的腳本，目前有看到我比較看得懂的有
1. [zeek intelligence feeds](https://github.com/CriticalPathSecurity/Zeek-Intelligence-Feeds) : 搜集目前公開的 IP 或 URL 黑名單加入 Zeek 中。
2. [BZAR](https://github.com/mitre-attack/bzar) : 根據 MITRE ATT&CK 進行攻擊策略分類。
### Zeek 輔助工具
不屬於 Zeek Scripts，但利用 Zeek 能產生出豐富且分類完善的 log 檔優勢，使用 Zeek 所產生的 logs 來進行分析，找出 Zeek 本身所沒辦法找出的問題。
1. [RITA](https://www.activecountermeasures.com/free-tools/rita/)
2. [AC-Hunter](https://www.activecountermeasures.com/ac-hunter/)
### 想法
經過這幾天的查找，感覺或許大家在使用上不是只有單純使用 Zeek 進行所有的偵查，也許是使用 Zeek 的 logs 來使用其他工具進行整體的分析。