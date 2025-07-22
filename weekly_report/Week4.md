---
tags:
  - 週進度
---
## 下次會議
### 會議時間：
### 會議地點：
### 會議目標：
## 週進度
### VM 資料備份
之前下載 RITA 導致 Zeek 內部出現問題而無法開啟([[0716]])，因此利用 timeshift 進行系統備份。使用下面指令來進行備份。
```bash
sudo timeshift --create --comments "<comments>" --tags D # Daily
```

參考資料：[link](https://dev.to/rahedmir/how-to-use-timeshift-from-command-line-in-linux-1l9b)
## 問題
>[!question] 以目前的技術上來看，Zeek 是有辦法裝在骨幹網路的各處如同 NetFlow 進行即時的網路分析嗎？
>以目前看來比較沒辦法，Zeek 的封包比起 NetFlow 需要的效能更高，以目前的研究來看會比較希望做前瞻性的測試，證明 Zeek 可以做到這些事情，再包裝之後可以做到什麼樣的事情。

>[!question] 我還是想做跟骨幹網路相關的研究，想知道目前 NetFlow 可以做到什麼事情？他有辦法針對流量進行即時的監控與分流嗎？
>NetFlow 目前可以做到 DDoS 的防禦，但分析的方式有點粗糙，好像是根據統計的結果，找出一個正常的基準，當超過基準過多時就進行封鎖。而現在也可以針對流量進行即時的監控了。

## meeting 內容

## meeting 回饋
