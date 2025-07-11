---
tags:
  - DVWA
---
## 介紹
全名 DAMN VULNERABLE WEB APPLICATION，讓使用者可以架設一個有漏洞的網站，裡面包括Brute Force、CSRF、SQL Injection、...等攻擊漏洞，讓使用者可以架設此網站來進行練習，測試攻擊的成功性。
## 使用方式
### 安裝
下載 @IamCarron 所撰寫的 scripts 來自動安裝套件與 DVAM 本身。
```bash
wget https://raw.githubusercontent.com/IamCarron/DVWA-Script/main/Install-DVWA.sh
chmod +x Install-DVWA.sh
sudo ./Install-DVWA.sh
```
因為我在 VM 中架設此網站，而 VM 本身沒有 GUI 介面所以無法開啟瀏覽器，但要登入網站需要使用瀏覽器進行登入。而剛好 VM 是沒有開啟防火牆的，所以本機開啟 VPN 後可以直接使用 `http://211.73.81.176/DVWA` 來進行登入。
### 開啟
開啟 apache2 來開啟 DVWA 網站
```bash
sudo systemctl start apache2
```
### 關閉
關閉 apache2 來關閉 DVWA 網站
```bash
sudo systemctl stop apache2
```
## 資源
DVWA：
- [Github](https://github.com/digininja/DVWA)

- [IT邦幫忙blog-DVWA安裝](https://ithelp.ithome.com.tw/articles/10334204)

- [SQLI using DVWA and SQLMAP video](https://www.youtube.com/watch?v=bEOWM6H99bk)
