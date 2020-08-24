# 4.8 使用AJAX 傳數據PHP文件\_網站聯繫表單

## 範例1-1

&lt;!DOCTYPE html&gt;

網站聯繫表單  
    body{  
  
      background-color: \#F2F3F5;  
    }  
   \#container{  
  
     padding-top: 60px;  
     width: 600px;  
     margin: auto;  
     font-family: "Helventica Neue" ,"Helventica","Arial";  
   }  
  
   .input-style{  
  
     border-radius: 5px;  
     border: 1px solid grey;  
     font-size: 1.1em;  
     padding-left: 20px;  
     margin-bottom: 10px;  
  
   }  
  
   .input-width{  
  
     width: 300px;  
     height: 40px;  
  
   }  
   \#mail-gender{  
     width: 323px;  
     height: 40px;  
  
   }  
  
   label{  
     width: 200px;  
     float: left;  
     font-size: 1.2em;  
     padding-top: 8px;  
   }  
  
   \#mail-message{  
  
     width: 500px;  
     padding-top: 15px;  
  
   }  
  
   \#submitButton{  
     background-color: \#AA47BC;  
     color: white;  
     width: 523px;  
     height: 40px;  
   }  
   .form-error{  
     color: red;  
   }  
  
  .form-success{  
     color: green;  
   }  
   .input-error {  
  
   box-shadow: 0 0 5px red;  
   }  
  
  
 姓 名  電子郵箱  性 別 男 性女 性 密 碼  確認密碼  發送郵件  
  
$\("\#validationForm"\).submit\(function\(event\){  
  
   event.preventDefault\(\);  
  
    var name = $\("\#email-name"\).val\(\);  
    var email =$\("\#email-address"\).val\(\);  
    var pass1 = $\("\#pass1"\).val\(\);  
    var pass2 = $\("\#pass2"\).val\(\);  
    var message = $\("\#mail-message"\).val\(\);  
    var submit = $\("\#submitButton"\).val\(\);  
     $\("\#error"\).load\("mail.php",{  
  
        name : name,  
        email : email,  
        pass1 : pass1,  
        pass2 : pass2,  
        message : message,  
        submit : submit,  
  
  
        }\);  
  
}\);  
  
  


## 範例1-2

mail.php

&lt;?php

if\(isset\($\_POST\["submit"\]\)\){ $name = $\_POST\["name"\]; $email = $\_POST\["email"\]; $pass1 = $\_POST\["pass1"\]; $pass2 = $\_POST\["pass2"\]; $message = $\_POST\["message"\];

```text
$errorEmpty = false;
$errorEmail = false;
$errorPass  = false;
```

if\(empty\($name\)\|\|empty\($email\)\|\|empty\($pass1\)\|\|empty\($pass2\)\|\|empty\($message\)\){

```text
 echo "<span class='form-error'>請輸入完整信息.</span>";
 $errorEmpty = true;
```

} elseif\(!filter\_var\($email,FILTER\_VALIDATE\_EMAIL\)\){

```text
 echo "<span class='form-error'>請輸入正確格式郵件地址.</span>";
 $errorEmail = true;
```

}elseif\($pass1 != $pass2\){

```text
  echo "<span class='form-error'>請確認您輸入相同密碼</span>";
   $errorPass = true;
```

}

}else{

```text
$mailToname = "adan.com";
$mailTo = "adanyao407@gmail.com";
$mailFromname =$name;
$mailFrom  =$email;
$mailSubject ="網站聯系表單";
$mailContent = "
 姓名: ".$name."
 信息內容:
 ".$message;

if(mail($mailTo,$mailSubject,$mailContent,$mailFrom)){
```

echo "Mail發送成功";

```text
 }else{

 echo "<span class='form-error'>Mail發送失敗</span>";

  }
```

} ?&gt;

  
  
   var errorEmpty = "&lt;?php echo $errorEmpty;?&gt;";  
   var errorEmail = "&lt;?php echo $errorEmail;?&gt;";  
   var errorPass  = "&lt;?php echo $errorPass;?&gt;";  
  
    if\(errorEmpty == true\){  
  
     $\("\#email-name, \#email-address,\#pass1,\#pass2,\#mail-message"\).addClass  
       \("input-error"\);  
    }  
  
  
     if\(errorEmail == true\){  
  
     $\("\#email-address\).addClass\("input-error"\);  
  
    }  
  
  
  
  
    if\(errorPass == true\){  
  
    $\("\#pass1, \#pass2"\).addClass\("input-error"\);  
  
    }  
  
  
  


```text
  echo $name."<br/>";
  echo $email."<br/>";
  echo $pass1."<br/>";
  echo $pass2."<br/>";
  echo $message."<br/>";
```

