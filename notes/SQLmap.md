---
tags:
  - sql_injection
  - python
---
## 介紹：
建立於python的框架，能對網站進行 SQL injection 的測試，針對特定網站能注入 payload 來測試網站進行 SQL injection，在注入攻擊後可以得到對應資訊。
## 使用方式
### 安裝
#### Linux
使用 git clone 來進行安裝，但需要在資料夾中進行。
```bash
git clone --depth 1 https://github.com/sqlmapproject/sqlmap.git sqlmap-dev
```
#### Mac
使用 Homebrew 來進行安裝。
```zsh
brew install sqlmap
```
### 使用
除了 url 之外，需要填入 --cookie 讓 sqlmap 能處於登入的狀態，需要測試過後在頁面原始碼找到 PHPSESSID 與 security 的參數填入 (於頁面中按 f12 後點選 application 側邊欄 Storage 中 Cookies 找到兩個參數)。
在攻擊 [[DVWA]] 時使用指令
```zsh
sqlmap -u http://211.73.81.176/DVWA/vulnerabilities/sqli_blind/\?id\=1\&Submit\=Submit\# --cookie="security=low; PHPSESSID=e9c7a3ui62jc2ekn00bhffrlku" --dbs --batch
```
#### Linux
```bash
python3 sqlmap
```
#### Mac
```zsh
sqlmap
```
## 資源：
- [基本指令介紹](https://hackmd.io/@bttea/sqlmap_common_parameters)
- [Github](https://github.com/sqlmapproject/sqlmap)
