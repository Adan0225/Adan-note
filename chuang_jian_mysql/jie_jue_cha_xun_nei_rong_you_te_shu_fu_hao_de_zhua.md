# 5.2解決查詢內容有特殊符號的狀況

## 範例

![](http://i.imgur.com/ZgDatVn.png)

&lt;?php $connection = mysqli\_connect\("sql106.byethost.com", "b24\_22957102", "dlink5229", "b24\_22957102\_demo0331"\);

if \(mysqli\_connect\_error\(\)\) {

```text
die("無 法 連 接 數 據 庫"."<br/>");
```

} $name = "Ke'lly";

$query = "SELECT name FROM `users` WHERE name = '**".mysqli\_real\_escape\_string\($connection, $name\)."'";**

if \($result = mysqli\_query\($connection, $query\)\) {

```text
  //echo mysqli_num_rows($result);



while ($row = mysqli_fetch_array($result )){


 print_r($row);
```

}

} else {

```text
   echo "無法找到相關內容";
```

}

?&gt;

