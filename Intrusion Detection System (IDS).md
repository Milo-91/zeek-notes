## 介紹
主要用於偵測網路中的惡意攻擊，會在許多地方建立檢查點，當出現惡意封包或異常現象時都會被搜集起來。其主要有兩種偵測方式：
### 1. Signature-based IDS
系統建立一個大型的資料庫儲存已知攻擊模式資料庫，將網路活動與資料庫內容進行比對，當出現匹配成功即視為攻擊發出警報。例如：
1. 針對 Log4j 等已知漏洞攻擊，其中 payload 會包含特定字串如 jakarta 或 jndi 等特定文字，進行文字比對就可以發現。
2. WannaCry 或 NotPetya 等勒索軟體在網路傳遞訊息時會產生特定檔案傳輸模式或 C2 通訊，簽章也可以檢查出此問題。
3. 已知的 IP 或 URL 建立的 Blacklist，也是屬於 signature-based IDS 處理範圍。
4. SQL Injection
### 2. Anomaly-based IDS
系統根據之前的網路活動方式建立正常行為數據模式，若網路活動偏離正常的基準線就會被視為異常。例如：
1. DDoS Attack
2. 非標準端口出現 HTTP 或 DNS request，代表可能是 DNS Tunnel。
3. 命令與控制 (C2)
4. SSH Brute Force
5. DNS Beaconing

>[!question] 什麼攻擊會是 Signature-based IDS 解決的？什麼攻擊是 Anomaly-based IDS 來解決的？

