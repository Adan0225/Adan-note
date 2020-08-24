# 9.3 瀏覽器及元素的常用函數及變量整理總結

```python
from selenium import webdriver
driver=webdriver.Firefox()
driver.get(r'http://www.baidu.com/')
print('driver attributes:')
print(dir(driver))
elem=driver.find_element_by_id('kw')
print('WebElement attributes:')
print(dir(elem))
```

其中：紅色加粗為數據（變量）。黑色加粗為方法（函數），函數的調用需要加括號哦。 什麼是屬性？屬性就是屬於一個對象的數據或者函數的元素（內建函數dir可查看對象屬性），可以通過屬性據點標識符來訪問。

瀏覽器屬性： driver attributes:

\['NATIVE\_EVENTS\_ALLOWED', '\_\_class\_\_', '\_\_delattr\_\_', '\_\_dict\_\_', '\_\_doc\_\_', '\_\_format\_\_', '\_\_getattribute\_\_', '\_\_hash\_\_', '\_\_init\_\_', '\_\_module\_\_', '\_\_new\_\_', '\_\_reduce\_\_', '\_\_reduce\_ex\_\_', '\_\_repr\_\_', '\_\_setattr\_\_', '\_\_sizeof\_\_', '\_\_str\_\_', '\_\_subclasshook\_\_', '\_\_weakref\_\_', '\_file\_detector', '\_is\_remote', '\_mobile', '\_switch\_to', '\_unwrap\_value', '\_wrap\_value', '**add\_cookie**', 'application\_cache', '**back**', 'binary', 'capabilities', '**close**', 'command\_executor', 'create\_web\_element', '**current\_url**', '**current\_window\_handle**', '**delete\_all\_cookies**', '**delete\_cookie**', 'desired\_capabilities', 'error\_handler', 'execute', 'execute\_async\_script', '**execute\_script**', 'file\_detector', **'find\_element', 'find\_element\_by\_class\_name', 'find\_element\_by\_css\_selector', 'find\_element\_by\_id', 'find\_element\_by\_link\_text', 'find\_element\_by\_name', 'find\_element\_by\_partial\_link\_text', 'find\_element\_by\_tag\_name', 'find\_element\_by\_xpath', 'find\_elements', 'find\_elements\_by\_class\_name', 'find\_elements\_by\_css\_selector', 'find\_elements\_by\_id', 'find\_elements\_by\_link\_text', 'find\_elements\_by\_name', 'find\_elements\_by\_partial\_link\_text', 'find\_elements\_by\_tag\_name', 'find\_elements\_by\_xpath'**, 'firefox\_profile', '**forward**', '**get**', '**get\_cookie**', '**get\_cookies**', 'get\_log', 'get\_screenshot\_as\_base64', '**get\_screenshot\_as\_file**', 'get\_screenshot\_as\_png', '**get\_window\_position**', '**get\_window\_size**', '**implicitly\_wait**', 'log\_types', '**maximize\_window**', 'mobile', 'name', 'orientation', '**page\_source**', 'profile', '**quit**', '**refresh**', 'save\_screenshot', 'session\_id', 'set\_page\_load\_timeout', 'set\_script\_timeout', 'set\_window\_position', '**set\_window\_size**', 'start\_client', 'start\_session', 'stop\_client', '**switch\_to**', 'switch\_to\_active\_element', '**switch\_to\_alert**', 'switch\_to\_default\_content', '**switch\_to\_frame**', '**switch\_to\_window**', '**title**', 'w3c', '**window\_handles**'\]

## 調用說明：

driver.屬性值

## 變量說明：

```bash
1.driver.current_url：用於獲得當前頁面的URL
2.driver.title：用於獲取當前頁面的標題
3.driver.page_source:用於獲取頁面html源代碼
4.driver.current_window_handle:用於獲取當前窗口句柄
5.driver.window_handles:用於獲取所有窗口句柄
```

## 函數說明：

```bash
1.driver.find_element*():定位元素，詳看另外一篇博文：Selenuim+Python之元素定位總結及實例說明
2.driver.get(url):瀏覽器加載url。
實例：driver.get("http//:www.baidu.com")
3.driver.forward()：瀏覽器向前（點擊向前按鈕）。
4.driver.back()：瀏覽器向後（點擊向後按鈕）。
5.driver.refresh()：瀏覽器刷新（點擊刷新按鈕）。
6.driver.close()：關閉當前窗口，或最後打開的窗口。
7.driver.quit():關閉所有關聯窗口，並且安全關閉session。
8.driver.maximize_window():最大化瀏覽器窗口。
9.driver.set_window_size(寬，高)：設置瀏覽器窗口大小。
10.driver.get_window_size()：獲取當前窗口的長和寬。
11.driver.get_window_position()：獲取當前窗口座標。
12.driver.get_screenshot_as_file(filename):截取當前窗口。
實例：driver.get_screenshot_as_file('D:/selenium/image/baidu.jpg')
13.driver.implicitly_wait(秒)：隱式等待，通過一定的時長等待頁面上某一元素加載完成。
若提前定位到元素，則繼續執行。若超過時間未加載出，則拋出NoSuchElementException異常。
實例：driver.implicitly_wait(10) #等待10秒
14.driver.switch_to_frame(id或name屬性值)：切換到新表單(同一窗口)。
若無id或屬性值，可先通過xpath定位到iframe，再將值傳給switch_to_frame()
15.driver.switch_to.parent_content():跳出當前一級表單。
該方法默認對應於離它最近的switch_to.frame()方法。
16.driver.switch_to.default_content():跳回最外層的頁面。
17.driver.switch_to_window(窗口句柄)：切換到新窗口。
18.driver.switch_to.window(窗口句柄):切換到新窗口。
19.driver.switch_to_alert():警告框處理。處理JavaScript所生成的alert,confirm,prompt.
20.driver.switch_to.alert():警告框處理。
21.driver.execute_script(js):調用js。
22.driver.get_cookies():獲取當前會話所有cookie信息。
23.driver.get_cookie(cookie_name)：返回字典的key為“cookie_name”的cookie信息。
實例：driver.get_cookie("NET_SessionId")
24.driver.add_cookie(cookie_dict):添加cookie。“cookie_dict”指字典對象，必須有name和value值。
25.driver.delete_cookie(name,optionsString):刪除cookie信息。
26.driver.delete_all_cookies():刪除所有cookie信息。
```

## 頁面元素屬性：

WebElement attributes:

\['\_\_class\_\_', '\_\_delattr\_\_', '\_\_dict\_\_', '\_\_doc\_\_', '\_\_eq\_\_', '\_\_format\_\_', '\_\_getattribute\_\_', '\_\_hash\_\_', '\_\_init\_\_', '\_\_module\_\_', '\_\_ne\_\_', '\_\_new\_\_', '\_\_reduce\_\_', '\_\_reduce\_ex\_\_', '\_\_repr\_\_', '\_\_setattr\_\_', '\_\_sizeof\_\_', '\_\_str\_\_', '\_\_subclasshook\_\_', '\_\_weakref\_\_', '\_execute', '\_id', '\_parent', '\_upload', '\_w3c', '**clear**', '**click**', 'find\_element', 'find\_element\_by\_class\_name', 'find\_element\_by\_css\_selector', 'find\_element\_by\_id', 'find\_element\_by\_link\_text', 'find\_element\_by\_name', 'find\_element\_by\_partial\_link\_text', 'find\_element\_by\_tag\_name', 'find\_element\_by\_xpath', 'find\_elements', 'find\_elements\_by\_class\_name', 'find\_elements\_by\_css\_selector', 'find\_elements\_by\_id', 'find\_elements\_by\_link\_text', 'find\_elements\_by\_name', 'find\_elements\_by\_partial\_link\_text', 'find\_elements\_by\_tag\_name', 'find\_elements\_by\_xpath', '**get\_attribute**', 'id', '**is\_displayed**', 'is\_enabled', '**is\_selected**', 'location', 'location\_once\_scrolled\_into\_view', 'parent', 'rect', 'screenshot', 'screenshot\_as\_base64', 'screenshot\_as\_png', '**send\_keys**', '**size**', '**submit**', '**tag\_name**', '**text**', 'value\_of\_css\_property'\]

## 調用說明：

```bash
driver.find_element*.屬性值
或
element=driver.find_element*
element.屬性值
```

## 變量說明：

```text
1.element.size:獲取元素的尺寸。
2.element.text：獲取元素的文本。
3.element.tag_name:獲取標籤名稱。
```

## 函數說明：

```bash
1.element.clear():清除文本。
2.element.send_keys(value):輸入文字或鍵盤按鍵（需導入Keys模塊）。
3.element.click()：單擊元素。
4.element.get_attribute(name):獲得屬性值
5.element.is_displayed():返回元素結果是否可見（True 或 False）
6.element.is_selected():返回元素結果是否被選中（True 或 False）
7.element.find_element*():定位元素，用於二次定位。
我的另一篇博文有提到：Python+Selenium定位不到元素常見原因及解決辦法（報：NoSuchElementException）
```

