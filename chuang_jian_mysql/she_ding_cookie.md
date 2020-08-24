# 5.4 設定cookies

ex:客戶網站購買東西，cookies 即會讓我們記得購買什麼？

## 範例1

&lt;?php

setcookie\("id","test", time\(\)+60\*60\);

echo $\_COOKIE\["id"\];

?&gt;

## 範例2

&lt;?php

setcookie\("id","test", time\(\)+60\*60\);

//echo $\_COOKIE\["id"\];

if\(count\($\_COOKIE\) &gt; 0\){

```text
  echo "Cookies已經設置";
```

} else {

```text
  echo "Cookies沒有被設置";
```

}

?&gt;

