# 10.3 Raspberry Pi3 使用在樹莓派上使用no-ip動態域名的方法

## 注意，如果沒有公網IP，本文的方法就不可行了。

首先，註冊一個noip.com的帳號。 註冊的步驟見這篇教程：[http://www.cnblogs.com/infopi/p/3991407.html](http://www.cnblogs.com/infopi/p/3991407.html)

### 建立目錄

第1行進入當前用戶的home目錄 第2行建立noip子目錄，第3行進入noip子目錄 cd ~ mkdir noip cd noip

### 下載noip客戶端源碼、安裝

第1行下載源碼，第2行解壓源碼，第3行進入解壓後的源碼目錄 第4行編譯，第5行安裝 wget [http://www.no-ip.com/client/linux/noip-duc-linux.tar.gz](http://www.no-ip.com/client/linux/noip-duc-linux.tar.gz) tar vzxf noip-duc-linux.tar.gz cd noip-2.1.9-1 make sudo make install

### 在安裝的過程中，會問以下問題

Please enter the login/email string for no-ip.com \(輸入註冊時填的郵箱地址\) Please enter the password for user \(輸入密碼\) Please enter an update interval: \[30\] \(noip客戶端檢查你路由器外部網址變化的間隔，默認是30分鐘\) \(Increments in minutes that you want no-ip client to check if your router’s external dynamic IP address has changed and updates it accordingly.\) Do you wish to run something at successful update? \[N\] \(y/N\) \(直接按回車即可\)

### 啟動noip客戶端，打這個命令：

sudo /usr/local/bin/noip2 要設置開機啟動，把上面這行加入/etc/rc.local，要加在exit 0那行以前

### 附兩個命令：

sudo /usr/local/bin/noip2 -C 重新配置一次（就是問安裝過程中那幾個問題） sudo /usr/local/bin/noip2 -S 顯示當前運行狀態、信息

### 經驗：

no-ip網頁上寫著“免費域名只能用30天、且有廣告”，根據我的經驗是這樣的： 1、要保持郵箱暢通，以便點擊郵件裡的鏈接激活域名。 2、如果不使用80端口，不會遇到廣告。 3、某些國內ISP會每幾天強制斷線、更換IP，這時noip會短暫失效，失效時間取決於設置的刷新間隔（默認30分鐘）。 轉貼網址：[http://www.cnblogs.com/infopi/p/3991437.html](http://www.cnblogs.com/infopi/p/3991437.html)

