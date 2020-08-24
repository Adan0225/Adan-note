# 1.網頁項目

## 網頁項目

### 網址

[https://openweathermap.org/forecast5](https://openweathermap.org/forecast5)

#### json editor online

[https://jsoneditoronline.org/\#/](https://jsoneditoronline.org/#/)

### json

[https://api.openweathermap.org/data/2.5/forecast?q=London,us&appid=d261eb9f0356977d7c38835f11fd8ea0&lang=zh\_tw](https://api.openweathermap.org/data/2.5/forecast?q=London,us&appid=d261eb9f0356977d7c38835f11fd8ea0&lang=zh_tw)

[https://api.openweathermap.org/data/2.5/forecast?q=London,us&appid=d261eb9f0356977d7c38835f11fd8ea0&lang=zh\_tw](https://api.openweathermap.org/data/2.5/forecast?q=London,us&appid=d261eb9f0356977d7c38835f11fd8ea0&lang=zh_tw)

#### index.php

&lt;!DOCTYPE html&gt;

天氣預報網站  
 .heroImage {  
   background-image: url\("weather\_bg.jpeg"\);  
   border-radius: 0;  
   height: 100vh;  
   margin-bottom: 0;  
   background-size: cover;  
 }  
 .alert{  
   display: none;  
 }  
  


## 天氣預報

請在如下輸入框輸入您要查詢的**城 市 名 稱**  查 詢查詢成功無法找到您查詢的城市，請重新再試.請輸入城市名稱!  
  
$\("\#findMyWeather"\).click\(function\(event\){  
  
  event.preventDefault\(\);  
  
  $\(".alert"\).hide\(\);  
  if\($\("\#city"\).val\(\)!= ""\){  
  
     $.get\("scraper.php?city="+$\("\#city"\).val\(\), function\(data\){  
       if\(data == ""\){  
         $\("\#fail"\).fadeIn\(\);  
       }else{  
         $\("\#success"\).html\(data\).fadeIn\(\);  
       }  
     }\);  
  }else{  
    $\("\#noCity"\).fadeIn\(\);  
  
  }  
}\);  
  
  
  
  


#### scraper.php

&lt;?php $city = $\_GET\["city"\];

//$city = str\_replace\(" ","-",$city\); //$city = "london"; $apiKey ="d261eb9f0356977d7c38835f11fd8ea0"; $contents = file\_get\_contents\("[https://api.openweathermap.org/data/2.5/forecast?q=".$city."&appid=".$apiKey."&lang=zh\_tw](https://api.openweathermap.org/data/2.5/forecast?q=".$city."&appid=".$apiKey."&lang=zh_tw)"\);

$contents = json\_decode\($contents, true\); $cityName = $contents\["city"\]\["name"\]; $description = $contents\["list"\]\[7\]\["weather"\]\[0\]\["description"\]; $temperature = $contents\["list"\]\[7\]\["main"\]\["temp"\]-273.15;

//print\_r\($temperature\);

$result = "城 市: ".$cityName.", 天 氣 狀 況： ".$description.", 溫 度: ".$temperature."℃";

if\($cityName != ""\){

echo $result;

}

?&gt;

