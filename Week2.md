---
tags:
  - 週進度
---
## 週進度
1. 於 VM 中成功執行 Zeek，並使用 zeekctl 來監測網卡資訊。
2. 架設 DVWA 並使用 sqlmap 進行 sql injection attack 並成功使用 zeek 於 notice.log 紀錄 sql injection attack 的警訊。
### 下週會議
會議時間：07/15 14:00~16:00
會議地點：404會議室
1. 介紹 zeek scripts 內容
2. zeek paper
## 問題
>[! question] 想了解正常你們在研究一項新事物時的研究方法，包括如何進行文獻搜索與模擬實驗。

>[! question] 我對實作的部分比較不擅長，我希望可以製作模擬攻擊來測試Zeek接收到的封包，但會有點不知道該怎麼下手，請問有什麼比較好的建議嗎？
>No comment。主要只有概念性的建議，有提醒我如果是會影響流量或服務的就不會直接上線。

>[! question] 你們會看logs，去確認是否有問題嗎？還是會使用腳本或套件來偵測危險，只有警訊出現才會檢查？
>以他們的架構來看，使用程式主動搜尋並找到結果比較合理，應該都是自動化的結果。
## meeting內容
### 1. NetFlow 架構介紹
NetFlow 為 Cisco Systems 所開發的網路協定，用來搜集與匯出 IP Header 資訊，包括 Source IP、Destination IP、Source port、Destination port、Layer 3 protocol、Input interface、Type of Service(ToS)...等資訊，使用 NetFlow 可以將網路的流向與資料量進行彙整，以便使用者加以利用。
國網中心使用NetFlow的技術加以改良，將Router的流量進行mirror，傳送至NetFlow機器中，再根據NetFlow所紀錄的流量資訊來進行診斷，根據流量大小來識別惡意攻擊，將識別出惡意攻擊的使用者阻擋在外。
NetFlow整個架構的主要優勢在於能將TWAREN流經的封包1:1進行抓取與紀錄，透過程式的過濾縮小需要紀錄的資料，讓伺服器能負荷NetFlow所有抓取的資料。
### 2. NICT 合作
與日本 NICT 公司進行合作，目標想要透過機器學習的方式辨別惡意攻擊的使用者。目前問題在於 NetFlow 所紀錄的資料無法進行 label，因 NetFlow 主要建立在流量多寡來判斷惡意行為，但流量來判斷本身不需要機器學習訓練來判斷，流量判斷以外的惡意行為是 NetFlow 無法分析也是 NICT 目前想要訓練的目標。
在 NICT 那邊有提供 darknet sensor，意旨有分配 IP address 但實際上沒有使用者的機器，類似於 Honeypot 功能，讓攻擊者嘗試對此機器進行攻擊後繼續攻擊模式與 IP address，列為惡意行為使用者。
### 3. Zeek 進度報告
介紹了 Zeek 基本的使用行為，可以 real-time 監控與 offline 的分析，也能使用 cluster mode 分散負載，腳本設計來客製化想要的資訊。在 VM 中安裝好 Zeek 並展示 logs 的內容。
她們對於 Zeek 的知識比我想像的要少一些，沒有完整介紹 build-in 的腳本與現有的監控能力讓她們對於 Zeek 的了解還不夠，本週將針對這方面進行研究，下週可以進行較完整的介紹。
## meeting回饋
她們回去討論要將 Zeek 安裝在哪裡會比較合適，但目前我只要在 VM 上面進行概念性驗證 (Proof of Concept, POC) 就好。
希望我可以針對 Zeek 能偵測出除了 NetFlow 能檢查的流量異常攻擊以外的攻擊模式研究，看看現有的腳本或是 Zeek 本身有沒有辦法檢查其他攻擊模式。先了解IDS都用來抵禦什麼攻擊與Zeek能不能針對這些攻擊來防禦。
希望可以使用 grafana 來進行呈現，這週打算研究 grafana 如何安裝於 VM 中並呈現 Zeek 的內容。
<mark class="hltr-r">主要目標是讓 NICT 端可以使用 Zeek 所檢查出的攻擊行為資料進行訓練，訓練好的模型再回去檢查 NetFlow 的資料。</mark>
