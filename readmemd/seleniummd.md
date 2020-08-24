# 9.1 Selenium 操作筆記

## 簡介

Selenium 是為瀏覽器自動化（Browser Automation）需求所設計的一套工具集合，讓程式可以直接驅動瀏覽器進行各種網站操作。

許多 Web Test Framework，都是以 Selenium API 作為基礎，藉此操作網頁表單資料、點選按鈕或連結、取得網頁內容並進行檢驗。

Selenium 2.0 帶來 WebDriver 的實作，Selenium WebDriver API 支援 Java、C\#、Ruby、Python 及 Perl 等多種語言，而且帶來跨越不同瀏覽器的自動化操作，目前 WebDriver API 規範已提交 W3C，若能夠被標準化且在各大瀏覽器實作，執行跨瀏覽器的自動化測試工作將會被簡化許多。

常見的 Web Driver：

* Mozilla GeckoDriver
* Google Chrome Driver
* SafariDriver
* Microsoft Edge Driver
* 更多

## 安裝 & 環境設定

* 安裝 Selenium
  * [http://www.seleniumhq.org/](http://www.seleniumhq.org/)
  * 以 Python 作為主要開發的語言
  * pip install -U selenium
* 安裝 Web Driver
  * [https://sites.google.com/a/chromium.org/chromedriver/](https://sites.google.com/a/chromium.org/chromedriver/) 
  * [https://github.com/mozilla/geckodriver/releases](https://github.com/mozilla/geckodriver/releases) 
  * [https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/) IEDriverServer.exe \(Only Windows Platform\)

### Chrome & Firefox Driver 下載&安裝

```bash
# chrome WebDriver
wget https://chromedriver.storage.googleapis.com/2.37/chromedriver_linux64.zip
unzip chromedriver_linux64.zip
cp chromedriver ~/anaconda3/bin/

# firefox WebDriver
wge https://github.com/mozilla/geckodriver/releases/download/v0.20.1/geckodriver-v0.20.1-linux64.tar.gz
tar xvf geckodriver-v0.20.1-linux64.tar.gz
cp geckodriver ~/anaconda3/bin/
```

```python
from selenium import webdriver
browser = webdriver.Chrome()
browser.get('https://qiang.taobao.com/')
```

```python
from selenium import webdriver
driver = webdriver.Firefox()
driver.get(r'http://www.baidu.com/')
```

