# Dlink\_DS2530\_for\_appium

## appium for android 查找元素方法總結

[http://blog.51cto.com/laomomo/1937024](http://blog.51cto.com/laomomo/1937024)

```python
from appium import webdriver
import time

desired_caps = {}
desired_caps['platformName'] = 'Android' 
desired_caps['platformVersion'] = '6.0' 
desired_caps['deviceName'] = 'vbox86p' 
desired_caps['appPackage'] = 'com.dlink.mydlink' 
desired_caps['appActivity'] = 'com.dlink.mydlink.lite20.LaunchActivity' 
driver = webdriver.Remote('http://localhost:4723/wd/hub', desired_caps) 
time.sleep(2)
driver.find_element_by_id("com.dlink.mydlink:id/buttonL").click()
time.sleep(4)
driver.find_element_by_id("com.dlink.mydlink:id/btnOK").click()
time.sleep(2)
driver.find_element_by_id("com.dlink.mydlink:id/edtAccount").send_keys("")
time.sleep(1)
driver.find_element_by_id("com.dlink.mydlink:id/edtPassword").send_keys("")
time.sleep(1)
driver.find_element_by_id("com.dlink.mydlink:id/btnSign").click()
```

