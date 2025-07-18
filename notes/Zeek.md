---
tags:
  - zeek
  - hybrid_IDS
related: "[[Intrusion Detection System (IDS)]]"
---
## 介紹
原名為 Bro，屬於 Hybrid [[Intrusion Detection System (IDS)|IDS]]，為一款開源的被動網路流量監控程式，也常被大家作為網路安全監控程式 (Network Security Monitor, NSM) 使用。最大能監控 10 Gigabit Ethenet (GE) 網路，主要使用事件觸發 (event trigger) 的方式來進行偵測，並使用 log 將不同類型的封包進行分類，像是conn.log紀錄所有的連線、http.log紀錄所有http的封包...等等。其優勢有三：
1. 能使用scripts來進行客製化監控提升靈活度，在Zeek預設環境中也有提供許多檢測特定攻擊的scripts檔可以直接使用。
2. 能針對多台主機進行Clusters的監控模式，意旨能不單依靠一台機器進行監控，而是進行工作分配，不同的機器監控不同的網路封包來平衡負載。
3. 除了能離線檢查.pcap檔案，也能針對特定的網卡進行即時封包檢測。

>[!question] 為什麼會說 Zeek 是 Hybrid IDS？感覺大家在使用上都不會用他 signature-based 的部分。
## 架構
下圖為Zeek運行架構圖，從網路接受到封包後會觸發Event Engine，Policy Script Interpreter針對不同事件寫入不同Logs或傳送Notification。

| ![[Zeek architecture.png]] |
| -------------------------- |
| <center> Zeek Architecture |

## 資源
### Zeek
- [documentation](https://docs.zeek.org/en/master/)
- [docker](https://hub.docker.com/r/zeek/zeek)
- [Github](https://github.com/zeek/zeek)

### Learn Zeek Logs
- [video](https://www.youtube.com/watch?v=a2Cp6VYQuvU)

### zeek ubuntu24.04 安裝
- [video](https://www.youtube.com/watch?v=YxvKCMuaoXA)
- [blog](https://www.atlantic.net/vps-hosting/how-to-install-zeek-network-security-monitoring-tool-on-ubuntu-24-04/)

### try zeek online
- [online web](https://try.zeek.org/#/tryzeek/saved/df33eba69af547b0a070fac53291454d)

### Training Day
- [video2022](https://www.youtube.com/watch?v=yBE4TrE6lhY&t=1569s)
- [Github](https://github.com/zeek/zeek-training/tree/master)
- [slide2024_intro-to-zeek](https://docs.google.com/presentation/d/11UidS9npqvTF7Cv2-8OQMDh-7u1gXWxS/edit?slide=id.g12925a13aa0_1_70#slide=id.g12925a13aa0_1_70)
- [[NSF-Summit-2024_Hands-on-Scripting.pdf |slide2024_hands-on zeek scripting]]
