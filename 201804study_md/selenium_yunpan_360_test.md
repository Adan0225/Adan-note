# 11.1selenium  yunpan 360 test

```python
from selenium import webdriver 
from selenium.webdriver.common.by import By
from selenium.webdriver.common.action_chains import ActionChains 
import time

#driver = webdriver.Firefox() 
driver = webdriver.Chrome()
driver.implicitly_wait(2)
driver.maximize_window()
driver.get("https://yunpan.360.cn/file/index") 
#driver.find_element_by_id("quc_account_191527156").clear() 
driver.find_element_by_css_selector("[name='account']").send_keys("") 
#dirver.find_element_by_id("password").clear() 
driver.find_element_by_css_selector("[name='password']").send_keys("") 
driver.find_element_by_css_selector('[type="submit"]').click() 
time.sleep(10)
js='document.getElementById("ui-id-2").style.display="none";'
driver.execute_script(js)
driver.find_element_by_class_name('ui-dialog-titlebar-close').click()
right_click = driver.find_element_by_css_selector("li[data-path='/Python test/']")
ActionChains (driver).context_click(right_click).perform()
```

