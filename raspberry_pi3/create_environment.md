# 10.1 Create environment

## Step1:

用 df -h 查詢SD卡屬於那個 /dev/sxxx

sudo umount /dev/sxx1  
sudo umount /dev/sxx2

sudo mkfs.ext4 /dev/sxx1 sudo mkfs.ext4 /dev/sxx2

再把 sda1 格式化為 ext4, 若想要查看是否硬碟格式是否正確為 ext4 , 可使用

sudo parted 進入到 parted 後, 鍵入print, 即可查看目前硬碟的格式

## Step2:

燒錄

用 dd 指令寫入 img 檔： sudo dd bs=1M if=2015-02-16-raspbian-wheezy.img of=/dev/sxx

or  
sudo dd bs=4M if=2015-02-16-raspbian-wheezy.img of=/dev/sxx 啟動 uart 用讀卡機讀取SD card 再從 /boot/config.txt 加入 **enable\_uart=1**, 就可以透過 /dev/ttyAMA0 通訊

透過gtkterm 登入 GTKTerm

## Step3:

enable wifi sudo iwlist wlan0 scan \| grep -i 'Iphone' sudo nano /etc/wpa\_supplicant/wpa\_supplicant.conf

network={ ssid="SSID" psk="WIFI PASSWORD" } Raspberry啟動SSH連線 enable ssh sudo raspi-config 新增使用者 sudo adduser james sudo usermod james -g sudo 登入的預設帳號/密碼為

pi/raspberry 進去之後，可以先執行以下指令換密碼

passwd pi 換完密碼，也順便執行

## Step4:

pppoeconf

sudo apt-get install pppoeconf

sudo pppoeconfi

id: seednet pw:seednet sudo reboot

ping 8.8.8.8

sudo raspi-config

interface enable ssh

sudo reboot

ssh pi@xxxx.xxxx.xxx.xxx &lt;-- pi

ip

psswd 改密碼

