---
tags:
  - 週進度
  - zeek
  - zeek_scripts
---
## 下次會議
### 會議時間：07/29 or 07/30
### 會議地點：
### 會議目標：
1. zeek + mcp
## 週進度
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
## 問題

>[! question] 昨天聽完組長的理想之後覺得製作上或許會跟 NICT 合作案路線不同，你們會希望朝哪個方向來做。
>希望我可以看 zeek 本身有什麼有趣的東西，用那個東西來發想，製作出一個小專案，讓他們之後可以使用。所以不用侷限於他們的計畫，可以做自己覺得有趣的東西，讓他們的計畫來湊這個小專案的內容。

## meeting 內容
### 1. Zeek Scripts
主要有跟他們說了，Zeek 能做的並非我們原本預期的那麼強大，他們也覺得我找的那些套件有的偵測，並非他們想要看到的東西。他們比較好奇，骨幹網路需要知道的攻擊，例如能否偵測 DDoS 攻擊、或是 C&C 的通訊封包，這些只有骨幹才能偵測並且做出防禦的攻擊是他們想要探討的。
### 2. Paper
有介紹 [[(Grace1)Refinements_In_Zeek_Intrusion_Detection_System.pdf|Grace1]] 給他們，也有跟他們說我覺得沒有參考價值。他們沒有 comments。
## meeting 回饋
首先應該會給我某個 honeypot 的 VM，讓我在上面部署 Zeek，看看在上面能不能看到更多的東西。
希望我去看 Zeek+MCP 看現在有沒有人拿來做什麼事情，這也是組長的藍圖中有的東西。
將這篇 [[(Grace2)A_Performance_Evaluation_of_Zeek-Based_Intrusion_Detection_in_Agricultural_IoT_Security.pdf|Grace2]] 看完。
<mark class="hltr-r">主要目標是希望我可以使用 Zeek 做出一套有趣的研究，他們再運用這個東西來了解 Zeek 可以幹嘛。</mark>
