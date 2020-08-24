# 11.2 D-Link  Router test

```python
from selenium import webdriver  
from selenium.webdriver.common.action_chains import ActionChains   
from selenium.webdriver.support.ui import Select  # 下拉選單
import time  

def set_channel(channel_num):
    time.sleep(1)
    # 進階設定 展開
    js='document.getElementById("RADIO_2GHz_adv").style.display="block";'
    driver.execute_script(js)

    time.sleep(1)
    s = driver.find_element_by_css_selector("select[id='channel_24'][onchange][sb]")
    num = s.get_attribute("sb")

    js='document.getElementById(\"sbOptions_'+ str(num) + '\").style.display=\"block\";'
    #print(js)
    driver.execute_script(js)
    # 抓取下拉選單元件
    time.sleep(2)
    js = "document.getElementById('channel_24').style.display='block'" 
    driver.execute_script(js)
    select = Select(driver.find_element_by_name("channel_24"))
    select.select_by_visible_text(str(channel_num))

    #for op in select.options:
    #    print(op.text)

    driver.find_element_by_css_selector("div[id='Save_btn']").click()
    time.sleep(15)
    driver.find_element_by_css_selector("div[id='Confirm_btn']").click()

if __name__ == "__main__":
    #driver = webdriver.Firefox()   
    driver = webdriver.Chrome()  
    driver.implicitly_wait(2)  
    driver.maximize_window()  
    driver.get("http://192.168.10.1/info/Login.html")   
    #driver.find_element_by_id("quc_account_191527156").clear()   
    # 登入
    driver.find_element_by_css_selector("[name='admin_Password']").send_keys("test1234")   
    #dirver.find_element_by_id("password").clear()   
    #driver.find_element_by_css_selector("[name='password']").send_keys("dlink5229")   
    driver.find_element_by_css_selector("#logIn_btn").click()

    # 基本設定
    time.sleep(2)
    driver.find_element_by_css_selector("a[id='menu_Settings']").click()
    time.sleep(4)
    driver.find_element_by_css_selector("a[href='javascript:CheckHTMLStatus(\"WiFi\");']").click()

    for channel_num in range(1, 12):
        #print(channel_num)
        set_channel(channel_num)
```

