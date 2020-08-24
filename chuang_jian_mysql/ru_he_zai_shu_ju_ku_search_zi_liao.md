# 5.1 如何在數據庫search  資料

## 範例1:

&lt;?php $connection = mysqli\_connect\("sql106.byethost.com", "b24\_22957102", "dlink5229", "b24\_22957102\_demo0331"\);

if \(mysqli\_connect\_error\(\)\) {

```text
die("無 法 連 接 數 據 庫"."<br/>");
```

}

$query = "SELECT  _FROM_ `users` _WHERE email LIKE '%new%'"; $query = "SELECT_  FROM `users` WHERE name = 'Kelly' AND password !=''";

if \($result = mysqli\_query\($connection, $query\)\) {

```text
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

## 範例2

&lt;?php $connection = mysqli\_connect\("sql106.byethost.com", "b24\_22957102", "dlink5229", "b24\_22957102\_demo0331"\);

if \(mysqli\_connect\_error\(\)\) {

```text
die("無 法 連 接 數 據 庫"."<br/>");
```

}

$query = "SELECT name FROM `users` WHERE 1";

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

