---
tags:
  - TWCC
  - vnc
  - tigervnc
---
## 介紹
全名 Virtual Network Computing，可以在 VM 中安裝 server 讓其他有螢幕的裝置進行有桌面的遠端操作。要使用 vnc 之前需要先安裝 vncserver 與桌面，我這次是安裝 tigervnc 與 xfce4 桌面。

## 使用方式
### 安裝
安裝 xfce4 桌面
```shell
sudo apt install xfce4 xfce4-goodies
```
安裝 tigervnc server
```shell
sudo apt install tigervnc-standalone-server
```
設定 vncpasswd
```shell
vncpasswd # 設定六位數密碼
```
新增 tigervnc 設定檔
```tigervnc.conf
# ~/.vnc/tigervnc.conf

$session="xfce4-session";
$geometry="1920x1080";
$AlwaysShared="yes";
$localhost="no";
```
設定啟動腳本
```xstartup
# /.vnc/xstartup

#!/bin/sh

# 清除 SESSION_MANAGER 和 DBUS_SESSION_BUS_ADDRESS，防止桌面啟動時出現錯誤
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS

# 啟動 XFCE 桌面環境
startxfce4

# 確保所有桌面組件都已啟動
[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -x /etc/X11/Xsession ] && exec /etc/X11/Xsession
```
可以寫 systemctl 來設定開機自動開啟，但我沒有成功就不寫了。

### 使用方式
在 terminal 中下啟動指令即可。
```shell
vncserver -fg
```
有什麼設定去看 man vncserver，裡面寫得蠻詳細的。