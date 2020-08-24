# DCS2530\_for\_web\_login

```python
#!/usr/bin/env python   
import time
from selenium import webdriver 
from selenium.webdriver.common.keys import Keys 

def login(driver):
    #driver = webdriver.Firefox() 
    driver.get("http://admin:3mZHkBbp@192.168.10.155") 
    driver.implicitly_wait(2)

    time.sleep(2)

    try:
        alert = driver.switch_to_alert()
        alert.accept()
        print("alert accepted")
    except:
        print("no alert")

if __name__ == "__main__":
    driver = webdriver.Chrome() 
    login(driver)
```

