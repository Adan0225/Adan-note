# 2.3jQuery 驗證表單

## jQuery 驗證表單

### 範例

&lt;!DOCTYPE html&gt;

 驗證表單

```text
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<script type="text/javascript" src="jquery.min.js"></script>
```

 body{

```text
  background-color: #F2F3F5;
}
```

## container{

```text
 padding-top: 60px;
 width: 600px;
 margin: auto;
 font-family: "Helventica Neue" ,"Helventica","Arial";
```

}

.input-style{

```text
 border-radius: 5px;
 border: 1px solid grey;
 font-size: 1.1em;
 padding-left: 20px;
 margin-bottom: 10px;
```

}

.input-width{

```text
 width: 300px;
 height: 40px;
```

}

## mail-gender{

```text
 width: 323px;
 height: 40px;
```

}

label{ width: 200px; float: left; font-size: 1.2em; padding-top: 8px; }

## mail-message{

```text
 width: 500px;
 padding-top: 15px;
```

}

## submitButton{

```text
 background-color: #AA47BC;
 color: white;
 width: 523px;
 height: 40px;
```

}

## error{

```text
 color: red;
```

}

&lt;/style&gt; &lt;/head&gt;

 姓 名  電子郵箱  性 別 男 性女 性 密 碼  確認密碼  發送郵件

  
  
$\("\#validationForm"\).submit\(function\(event\){  
    var errorMessage ="";  
   event.preventDefault\(\);  
   var name = $\("\#email-name"\).val\(\);  
   var email =$\("\#email-address"\).val\(\);  
   var pass1 = $\("\#pass1"\).val\(\);  
    var pass2 = $\("\#pass2"\).val\(\);  
    var message = $\("\#mail-message"\).val\(\);  
  
    function isValidEmailAddress\(emailAddress\){  
  
      var pattern = /^\b\[A-Z0-9-\]+@\[A-Z0-9\]+\.com\b/i;  
  
      return pattern.test\(emailAddress\);  
  
    }  
    if\(name == "" \|\| email == "" \|\| pass1 == "" \|\| pass2 == "" \|\| message == ""\){  
      errorMessage = "請輸入完整訊息.";  
    }else if\(!isValidEmailAddress\(email\)\){  
  
      errorMessage ="請輸入正確格式的郵箱地址.";  
    }else if\(pass1 != pass2\){  
  
      errorMessage ="請確認您輸入的密碼."  
    }  
    if \(errorMessage ==""\){  
     $\("\#error"\).html\("郵件已發送!"\);  
     $\("\#error"\).css\("color","green"\);  
  } else{  
    $\("\#error"\).html\(errorMessage\);  
    $\("\#error"\).css\("color","red"\);  
  
  }  
}\);  
  
  


&lt;/body&gt; &lt;/html&gt; 

