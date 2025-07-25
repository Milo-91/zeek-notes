---
tags:
  - 週進度
---
## 下次會議
### 會議時間：7/29 14:00
### 會議地點：[視訊會議]([https://teams.microsoft.com/l/meetup-join/19%3ameeting_YmMxYTFkNGMtZGZmYy00YWNmLWJkYjUtZDZkYzYxMWMwYzk2%40thread.v2/0?context=%7b%22Tid%22%3a%225971958d-ee58-4751-a077-feff48b33d00%22%2c%22Oid%22%3a%22ba8ee0ad-d434-4ff9-85b8-7f5d7e988f66%22%7d](https://www.google.com/url?q=https://teams.microsoft.com/l/meetup-join/19%253ameeting_YmMxYTFkNGMtZGZmYy00YWNmLWJkYjUtZDZkYzYxMWMwYzk2%2540thread.v2/0?context%3D%257b%2522Tid%2522%253a%25225971958d-ee58-4751-a077-feff48b33d00%2522%252c%2522Oid%2522%253a%2522ba8ee0ad-d434-4ff9-85b8-7f5d7e988f66%2522%257d&sa=D&source=calendar&usd=2&usg=AOvVaw0Yq03plvdf6kKMDSemA0ie))
### 會議目標：
1. 介紹 Zeek + MCP
2. 介紹 100G 報告內容
## 週進度
### VM 資料備份
之前下載 RITA 導致 Zeek 內部出現問題而無法開啟([[0716]])，因此利用 timeshift 進行系統備份。使用下面指令來進行備份。
```bash
sudo timeshift --create --comments "<comments>" --tags D # Daily
```

參考資料：[link](https://dev.to/rahedmir/how-to-use-timeshift-from-command-line-in-linux-1l9b)
### Grafana Zeek
有將 Zeek 的資料成功丟到 Grafana 上面了，但因為沒有找到適合的 Dashbaord，所以現在只停留在資料連接到 Grafana 的部分。
### Honeypot
已經在 Honeypot 上面裝上 Zeek，並部署上去了，但不知是否因為資料量過大，目前無法使用 ssh 連線上 VM。
## 問題
>[!question] 以目前的技術上來看，Zeek 是有辦法裝在骨幹網路的各處如同 NetFlow 進行即時的網路分析嗎？
>以目前看來比較沒辦法，Zeek 的封包比起 NetFlow 需要的效能更高，以目前的研究來看會比較希望做前瞻性的測試，證明 Zeek 可以做到這些事情，再包裝之後可以做到什麼樣的事情。

>[!question] 我還是想做跟骨幹網路相關的研究，想知道目前 NetFlow 可以做到什麼事情？他有辦法針對流量進行即時的監控與分流嗎？
>NetFlow 目前可以做到 DDoS 的防禦，但分析的方式有點粗糙，好像是根據統計的結果，找出一個正常的基準，當超過基準過多時就進行封鎖。而現在也可以針對流量進行即時的監控了。

>[!question] 我們想使用 MCP 來串接 Zeek，是預期 Zeek 本身就有分辨攻擊的能力嗎？還是希望使用 LLM 來根據 logs 分辨是否有攻擊？也想知道原本要架設 IDS 的理由。

## meeting 內容

## meeting 回饋
