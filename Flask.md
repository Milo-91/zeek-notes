---
tags:
  - web
  - python
---

## 介紹
Python內部的一個輕量級網頁框架，可以輕鬆架設網頁伺服器。
基本的使用只有五行程式

```python
from flask import Flask
app = Flask(__name__) # 固定用法，傳入__name__參數代表當前模組名稱
@app.route("/") # 裝飾器，告訴Flask哪個URL會觸發下面的function
def hello():
	return "Hello"
```

## 資源
- [教學網站](https://ithelp.ithome.com.tw/articles/10258223?sc=pt)
