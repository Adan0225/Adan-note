# 9.5 webdriver+selenium面試總結

## 1. WebDriver原理

webDriver是按照`client/server模式設計`，`client`就是我們的`測試代碼`，發送請求，`server就是打開的瀏覽器來打開client發出的請求並做出響應`。

具體的工作流程：

·webdriver打開瀏覽器並綁定到指定端口。啟動的瀏覽器作為remote server.

·client通過commandExecuter發送httpRequest給remote server的的偵聽端口（the webdriver wire control通信協議）

·Remote server根據原生的瀏覽器組件來轉化為瀏覽器的native調用。

備註：啟動瀏覽器的時候，使用的是http: hyper test transfer protocol

## 2. Selenium 特點和組成

`Selenium是一個針對web應用的開源測試框架`，它的測試用例可以用html table或者html 代碼或者編程語言進行開發，而且他能在幾乎所有的現在的瀏覽器上執行。Selenium可以被部署到windows.linux.mac平臺上，支持的語言有java/python/ruby/.net/perl

特點：

·支持錄製回放

·多種方式對頁面元素進行定位並操作

·能夠及進行debug和設置斷點

·能夠把測試腳本保存成html/ruby或者其他語言

·支持user-extensions.js形式的用戶擴展

·能夠進行頁面的斷言

1\) Selenium IDE: 是firefox的插件，可以錄製/回放/測試腳本

2\) Selenium RC：支持程序語言（java/C\#/python/ruby）編寫測試用例; selenium和其他測試框架集成，比如java環境下將selenium和Junit集成，利用selenium來書寫測試用例，用Junit來實現測試用例的自動化運行。

3\) Selenium Core：是selenium的核心，是有js和html文件組成，它是selenium IDE和selenium RC的核心引擎。

4\) Selenium Grid：是selenium的擴展，可以將一批selenium腳本分配到不同的測試機上同步運行。即selenium grid可以在不同的主機上建立主節點\(hub\)和分支節點\(node\), 可以使主節點上的測試用例在不同的分支節點上運行。對於不同的節點來說，可以搭建不同的測試環境（操作系統/瀏覽器）。

## 3. Selenium內部運行機制

## 4. 如何提高自動化腳本穩定性

找原因

1\)網速原因，增加時間等待

2\)函數原因，儘量少使用容易衝突的函數

3\)配置testNG實現多線程，在編寫測試用例的時候，一定要實現鬆耦合，在服務器允許的情況下儘量設置多線程運行，提高執行速度。

## 5. 高質量自動化腳本特點

業務和代碼分離，封裝型好。

自動化用例耦合性低，獨立性強，易於擴展維護

## 6. 自動化測試缺陷

不穩定

可靠性不強

不易維護

成本與收益

## 7. 自動化用例的執行策略

根據自動化執行的目的來決定

（1）自動化測試用例執行用來監控，可以設置用例定時執行；

（2）用於迴歸測試，可以把測試用例設置成觸發式執行；

（3）不需要經常執行的測試用例，可以由人工執行。

## 8. 提高selenium腳本的執行速度方式

（1）減少操作步驟，減少不必要的操作；

（2）中斷頁面加載，如果頁面加載內容過多並且加載的內容不影響我們測試，可以設置超時時間，中斷頁面加載；

（3）設置等待時間的時候，可以sleep\(\)固定的時間，檢測到元素出現後中斷等待也可以提高速度；

（4） 配置testNG實現多線程，在編寫測試用例的時候，一定要實現鬆耦合，在服務器允許的情況下儘量設置多線程運行，提高執行速度。

## 9. 元素定位

1\) Id定位

find\_element\_by\_id\(‘kw’\) //通過id屬性定位

2\) Name定位

find\_element\_by\_name\(‘wd’\) //通過名字進行定位，名字一般不唯一，一般不能 通 過其定位

3\) ClassName定位

find\_element\_by\_class\_name\(‘cn’\) //通過類名進行定位

4\) TagName定位

find\_element\_by\_tag\_name\(‘input’\) //標籤，一般用於一類元素的定位

5\) LinkText定位

find\_element\_by\_link\_text\(‘新聞’\) //文本鏈接定位

6\) PartialLinkText定位

find\_element\_by\_partial\_link\_text\(‘一個很長的’\) //文本鏈接的部分文字

7\) 絕對路徑定位

find\_element\_by\_xpath\(‘/html/body/div/div\[2\]/form/span/input\[2\]’\) //絕對地址定位， 利用層級定位

find\_element\_by\_xpath\(‘//input\[@name=’n’ and id=’kw’\]’\) //當前頁面某個目錄下 name為n，id為kw的input標籤，利用元素屬性進行定位

find\_element\_by\_xpath\(‘//_\[@id=kw\]’\) //其中_表示任何屬性，表示id為kw的任何屬 性的元素

find\_element\_by\_xpath\(‘//span\[@class=’c’\]/input’\) //層級和屬性結合進行定位

find\_element\_by\_xpath\(‘//a\[contains\(href , ’test’\)\]’\)

8\) 相對路徑定位

相對路徑定位一般比絕對路徑定位快。

```text
   find_element_by_css_selector(‘.class1’) // 類名定位 .class
```

find\_element\_by\_css\_selector\(‘\#id’\) //id定位 \#id

find\_element\_by\_css\_selector\(‘input’\) // 標籤名定位

find\_element\_by\_css\_selector\(‘\[autocomplete=off\]’\) //屬性定位

find\_element\_by\_css\_selector\(‘span&gt;input’\) //標籤名為span的input子元素

9\) 定位一組元素

Checkboxes = find\_elements\_by\_tag\_name\(‘checkbox’\)

for checkbox in Checkboxes:

checkbox.click\(\) \# 通過for循環全選所有的checkbox

Checkboxes.pop\(\).click\(\) \#取消勾選一些checkbox，pop\(-1\)=pop\(\)表示一組元素的最後一個；pop\(0\) 表示一組元素的第一個，pop\(1\)表示一組元素的第二個，以此類推

10\) 父子/兄弟/相鄰節點的定位

·父-&gt;子

Find\_element\_by\_id\(‘parent’\).find\_element\_by\_tag\_name\(‘input’\) 串聯尋找

Find\_element\_by\_xpath\(‘//input/div\[@name=’n’\]/span/input\[1\]’\) xpath的層級

Find\_element\_by\_css\_selector\(‘div\#b&gt;input’\) css selector的父子關係

·子-&gt;父

Find\_element\_by\_xpath\(‘//div\[@id=’c’\]/../..’\) 其中//div\[@id=’c’\]的父親的父親

·哥哥-&gt;弟弟

Find\_element\_by\_xpath\(‘//div\[@id=’c’’/../div\[1\]\) 找到弟弟後找父親然後找哥哥

Find\_element\_by\_css\_selector\(‘div\#d+div’\) 表示id=d的div後面緊跟著的div

Find\_element\_by\_css\_selector\(‘div\#d~div’\) 表示id=d的div後面同一級所有div

11\) 二次定位

Element1 = driver.find\_element\_by\_id\(‘ID1’\)

Element2 = Element1.find\_element\_by\_id\(‘ID2’\)

12\) display: none 和hidden的區別

共同點：把網頁中的某個元素隱藏起來；他們在selenium中都是定位不到的。

區別：display:none不為隱藏的對象保留其物理空間，該對象在這個頁面上徹底消失，看不到/摸不到；hidden使對象在網頁上不可見，但該對象在網頁中依然佔有空間，看不到/摸得到。

備註：isElementPresent\(\)來判斷元素是否存在。

## 10. 常見控件使用

1\) link/button:

element.click\(\)

注：ajax不能使用clickAndWait\(\)函數，因為cickAndWait函數會在click之後等待頁面重新加載完成，而ajax是部分刷新，所以這個頁面不能重新加載完成。

2\) Textbox:

element.send\_keys\(‘test’\)

3\) Upload

Driver.find\_element\_by\_id\(‘id’\).send\_keys\(‘D\test.txt’\)

4\) Mouse Event:

e1=driver.find\_element\_by\_id\(‘kw’\)

ActionChains\(driver\).double\_click\(\)/.context\_click\(\)/.drag\_and\_drop\(\)/.move\_to\_eleme nt\(\)/.perform\(\) \# 雙擊/右擊/拖動/懸停/執行actionChains中的行為

5\) Dropdown:

·標籤的下拉菜單

from selenium.webdriver.support.ui import Select

Select\(driver.find\_element\_by\_id\(‘gender’\)\).select\_by\_index\(1\)

Select\(driver.find\_element\_by\_id\(‘gender’\)\).select\_by\_value\(“2”\)

Select\(driver.find\_element\_by\_id\(‘gender’\)\).select\_by\_visible\_text\(“Male”\)

·非標籤的下拉菜單

Dropdown1 = driver.find\_element\_by\_id\(‘id’\) \#先定位到dropdown

Dropdown1.find\_element\_by\_id\(“li2\_input\_2”\) \#再定位到dropdown中的值

6\) Alert:

driver.switch\_to.alert.accept\(\)//接受

driver.switch\_to.alert.dismiss\(\) //取消

Message=driver.switch\_to.alert.text //獲取彈窗的文本消息

driver.switch\_to.alert.send\_keys\(‘hello’\) //輸入值,這個在alert和confirm中不可用

7\) Window

Driver.refresh\(\) 刷新

Driver.back\(\) 後退

Driver.forward\(\) 前進

Driver.maximize\_window\(\) 最大化

Driver.set\_window\_size\(100,200\) 設置窗口大小

Driver.switch\_to.window\(searchwindow\)

8\) Frame

Driver.switch\_to.frame\(ReferenceFrame\)

Driver.switch\_to.parent\_frame\(\) \# frame需要一級一級切

Driver.switch\_to.default\_content\(\)

## 11. 等待

1\) 顯式等待

等待某個條件成立時繼續執行，每隔一段時間進行檢測，超出最大時間 則拋出異常（程序每隔X秒看一眼，如果條件成立，執行下一步，否則等待，超出最大 時間，拋出異常）

From selenium.webdriver.common.by import By

From selelnium.webdirver.support.ui import WebDriverWait

From selenium.webdriver.support import expected\_conditions as EC

E = WebDriverWait\(driver, 5,0.5\).until\(

EC.presence\_of\_element\_located\( \(By.ID, ‘kw’\) \)

\)

2\) 隱式等待

隱式等待中的時間並非一個固定的等待時間，它並不影響腳本的執行速度。比如進行某元素的定位時，如果元素可以定位就繼續執行，如果目前定位不到就以輪詢的方式持續判斷該元素是否被定位到，如果超過規定的時間還沒定位到就拋出異常。（甲約乙去吃飯，甲在這裡等著，等了10分鐘乙到達，則從10分鐘之後開始下一步，假如等了20分鐘，則20分鐘後開始下一步，如果到了最大時間30分鐘還沒到就拋異常）

driver.implicitly\_wait\(20\)

3\) 強制等待

From time import sleep

Sleep\(2\)

## 12. 截圖

driver.get\_screenshot\_as\_file\('E:\sc.jpg'\)

## 13. 線性測試

開發維護成本高

## 14. 模塊化驅動測試

將重複的操作獨立為公共模塊，儘量消除重複，提高測試用例的可維護性。

## 15. 數據驅動測試

數據參數化

1\) 讀取txt文件

File= open\(‘E:\wtest.txt’, ‘r’\)

Lines = File.readlines\(\)

For line in lines:

User = line.split\(‘,’\)\[0\]

Passw=line.split\(‘,’\)\[1\]

Print\(User, Passw\)

2\) 讀取csv文件

UnicodeDecodeError （未找到解決方案）

3\) 讀取xml文件

## 16. 關鍵字驅動測試

腳本/數據/業務 分離

## 17. page object設計模式

是將page對象封裝成一個HTML頁面，通過提供的應用程序特定的API來操作頁面元素，而不是在html中來搜尋對象，即提供一個易於編程的接口並隱藏窗口中底層的部件，對界面的交互細節進行封裝。

優點是：減少了代碼的重複/提高測試用例的可讀性/提高測試用例的可維護性（特別是UI頻繁變化的項目）

page object設置模式中，不需要在page裡定位的方法中加上斷言（why）

## 18. Assert斷言

-斷言的英文是assertion，斷言檢查的英文是assertion checking。

-斷言是指定一個程序必須已經存在的狀態的一個邏輯表達式，或者一組程序變量在程序執行期間的某個點上必須滿足的條件。

Assert判斷如果出現錯誤，則會中斷整個測試；使用verify進行判斷如果出現錯誤仍會繼續執行直到結束。

