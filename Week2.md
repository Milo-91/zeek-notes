---
tags:
  - 週進度
---
## 週進度

## 問題
>[! question] 想了解正常你們在研究一項新事物時的研究方法，包括如何進行文獻搜索與模擬實驗。

>[! question] 我對實作的部分比較不擅長，我希望可以製作模擬攻擊來測試Zeek接收到的封包，但會有點不知道該怎麼下手，請問有什麼比較好的建議嗎？

>[! question] 你們會看logs，去確認是否有問題嗎？還是會使用腳本或套件來偵測危險，只有警訊出現才會檢查？
## meeting內容
### 1. NetFlow 架構介紹
NetFlow 為 Cisco Systems 所開發的網路協定，用來搜集與匯出 IP Header 資訊，包括 Source IP、Destination IP、Source port、Destination port、Layer 3 protocol、Input interface、Type of Service(ToS)...等資訊，使用 NetFlow 可以將網路的流向與資料量進行彙整，以便使用者加以利用。
國網中心使用NetFlow的技術加以改良，將Router的流量進行mirror，傳送至NetFlow機器中，再根據NetFlow所紀錄的流量資訊來進行診斷，根據流量大小來識別惡意攻擊，將識別出惡意攻擊的使用者阻擋在外。
NetFlow整個架構的主要優勢在於能將TWAREN流經的封包1:1進行抓取與紀錄，透過程式的過濾縮小需要紀錄的資料，讓伺服器能負荷NetFlow所有抓取的資料。
### 2. NICT 合作
與日本 NICT 公司進行合作，目標想要透過機器學習的方式辨別惡意攻擊的使用者。目前問題在於 NetFlow 所紀錄的資料無法進行 label，因 NetFlow 主要建立在流量多寡來判斷
### 3. Zeek 進度報告
## meeting回饋
