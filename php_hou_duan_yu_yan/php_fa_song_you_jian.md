# 4.5 PHP 發送郵件

## 範例

&lt;?php

$emailTo = "adanyao@gmail.com"; $title = "Test Email"; $body = "That is test email content."; $headers = "From: myEmail@address.com";

if \(mail\($emailTo,$title,$body,$headers\)\){

```text
 echo "郵件發送成功!";
```

} else {

```text
 echo "郵件發送失敗!";
```

}

?&gt;

