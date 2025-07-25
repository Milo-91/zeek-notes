---
tags:
  - python
  - venv
---
## 介紹
python 套件中的虛擬環境。在某些程式會需要的版本與其他程式可能不同會造成版本衝突，為了讓程式可以順利執行，使用虛擬環境來客製化環境。

venv 會改變電腦中的環境變數，製作出獨立的 python 與 pip 環境，讓使用者可以架設不同版本的套件。
## 常用指令
```shell
# 製作新的虛擬環境
python3 -m venv <venv_name>
# 開啟虛擬環境
source <venv_name>/bin/activate
# 關閉虛擬環境
deactivate
```
