# 2.2 AJAX

1.Ajax\(Asynchronous Java Script and XML\) 提高用戶訪問網頁的速度

[https://jquery.com/download/](https://jquery.com/download/)

Using jQuery with a CDN

Google CDN

[https://developers.google.com/speed/libraries/devguide\#jquery](https://developers.google.com/speed/libraries/devguide#jquery)

 \#\#範例: index.htmlLearing AJAX  
  
 提 交

  
  
 // $.get\("test.txt", function\(data\){  
 //      alert\(data\);  
 //  
 //    }\);  
$.ajax\({  
  url:"test.html"  
}\).done\(function\(data\){  
  // alert\(data\)  
}\);  
  $\(document\).ready\(function\(\){  
    $\("button"\).click\(function\(\){  
      $.get\("test.html",function\(data,status\){  
        // alert\(status\);  
        $\("\#result"\).html\(data\);  
      }\);  
  
    }\);  
  }\);  
  
  
  


&lt;/body&gt; &lt;/html&gt;

test.html 這是一個test.html更改之後的網頁內容

