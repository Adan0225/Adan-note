# 5.創建mySQL

[http://cpanel.byethost.com/](http://cpanel.byethost.com/)

使用phpMyadmin+MySQLDB

## 如何連接mySQL 數據庫

## 增加及更新數據資料

&lt;?php $connection = mysqli\_connect\("sql106.byethost.com", "b24\_22957102", "dlink5229", "b24\_22957102\_demo0331"\);

if \(mysqli\_connect\_error\(\)\) {

```text
die("無 法 連 接 數 據 庫"."<br/>");

//echo "無 法 連 接 數 據 庫";
```

}

//echo "繼 續 運 行 代 碼";

//$query = "SELECT \* FROM `users` WHERE 1 ";

//$query = "INSERT INTO users \(name, email, password\) VALUES\('Kelly' , 'kelly@gmail.com', 'newpass'\)";

$query = "UPDATE users SET email ='kelly@newgmail.com' WHERE name = 'kelly' LIMIT 1";

if \($result = mysqli\_query\($connection, $query\)\) {

```text
// echo "已經找到相關內容";

$row = mysqli_fetch_array($result );
 print_r($row);
```

} else {

```text
   echo "無法找到相關內容";
```

}

?&gt;

