# 安裝環境

## 模擬器安裝

```bash
sudo apt-get install virtualbox
sudo chmod u+x genymotion-2.12.0-linux_x64.bin
./genymotion-2.12.0-linux_x64.bin 


需要設定BIOS 打開CPU 虛擬技術
```

## 讓Genymotion支持Arm Cpu

[https://www.cmgine.com/archives/7291.html](https://www.cmgine.com/archives/7291.html)

Genymotion模擬器引起的Address already in use ADB server didn't ACK

[https://blog.csdn.net/m\_changgong/article/details/51730664](https://blog.csdn.net/m_changgong/article/details/51730664)

or

copy android-sdk-linux 下面的 adb ~/.mybin

## Appium環境搭建

* 安裝andriod sdk和java jdk

```bash
sudo apt-get install nodejs
sudo apt-get install npm

// 1.安裝node管理 n
sudo npm install -g n 
// 2. 降低版本，更新npm
sudo n 6

sudo apt-get install openjdk-8-jdk


export ANDROID_HOME="/media/shihyu/Toshiba/vr_sdk_ndk/android-sdk-linux"

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export JRE_HOME=${JAVA_HOME}/jre 
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
export JRE_HOME=${JAVA_HOME}/jre 
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
```

## 安裝appium

```bash
sudo npm install -g appium
sudo npm install -g appium-doctor
```

安裝appium-client

clinet支持多個語言版本，如python，java，ruby等等，這裡安裝python。

```bash
sudo pip install selenium
sudo pip install Appium-Python-Client
```

安裝python3.4版本的話，使用如下命令：

```bash
sudo pip3 install selenium
sudo pip3 install Appium-Python-Client
```

檢測環境是否搭建完畢

```bash
appium-doctor
```

結果

```bash
Running Android Checks
✔ ANDROID_HOME is set to "/usr/local/android-sdk-linux"
✔ JAVA_HOME is set to "/usr/lib/jvm/java-7-openjdk-amd64."
✔ ADB exists at /usr/local/android-sdk-linux/platform-tools/adb
✔ Android exists at /usr/local/android-sdk-linux/tools/android
✔ Emulator exists at /usr/local/android-sdk-linux/tools/emulator
✔ Android Checks were successful.

✔ All Checks were successful
```

說明環境OK，出錯的話，請修改。

```bash
appium &
```

後臺運行appium.

編寫測試用例，啟動計算器

```python
from appium import  webdriver

desired_caps = {}
desired_caps['platformName'] = 'Android'
desired_caps['platformVersion'] = '8.0'
desired_caps['deviceName'] = 'vbox86p'
desired_caps['appPackage'] = 'com.android.calculator2'
desired_caps['appActivity'] = '.Calculator'

driver = webdriver.Remote('http://localhost:4723/wd/hub', desired_caps)
```

chmod +x test.py

Android連接到PC，啟動usbdebug.

python test.py

編寫練習腳本test.py：

```python
from appium import webdriver

desired_caps = {}

desired_caps['platformName']
= 'Android'

desired_caps["platformVersion"]
= '4.1'

desired_caps["deviceName"]
= '192.168.56.101:5555'

desired_caps["appPackage"]
= 'com.sogou.se.sogouhotspot'

desired_caps['appActivity']
= '.MainActivity'

driver =
webdriver.Remote('http://localhost:4723/wd/hub', desired_caps)

sleep(1)

driver.find_element_by_name('頭條').click()
```

【這裡說明一下,deviceName,appPackage,appActivity都可以通過adb命令獲取到】

```bash
adb devices
adb shell pm list package
adb shell dumpsys activity
```

## 參考

[http://www.iloveandroid.net/2015/10/20/studyAppium\_1/](http://www.iloveandroid.net/2015/10/20/studyAppium_1/)

