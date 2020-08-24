# 5.3 Session 變量

## 範例

### session\_unset\(\);移除變量的值

&lt;?php session\_start\(\);

```text
 print_r($_SESSION["name"]);

 $_SESSION["name"] = "Andrew";

 //print_r($_SESSION["name"]);

 session_unset();

 //session_destory();

 echo "我清除SESSION變量後的值是:" .$_SESSION["name"].".";
```

?&gt;

