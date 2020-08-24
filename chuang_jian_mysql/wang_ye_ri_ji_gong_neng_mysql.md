# 5.6 網頁秘密日記 註冊帳號功能

## 新增帳號：Name、Email、Password

&lt;?php

if \($\_POST\['submit'\]\) {

```text
$error = "";

if (!$_POST['userName'])
    $error .= "<br/>Please enter your name";

if (!$_POST['userEmail'])
    $error .= "<br/>Please enter your email";
else if (!filter_var($_POST['userEmail'], FILTER_VALIDATE_EMAIL))
    $error .= "<br/>Please enter a valid email address";

if (!$_POST['userPassword'])
    $error .= "<br/>Please enter your password";
else {
    if (strlen($_POST['userPassword']) < 8)
        $error .= "<br/>Please enter a password with minimum 8 characters";
    if (!preg_match('`[A-Z]`', $_POST['userPassword']))
        $error .= "<br/>Please include a capital letter in your password";
}

if ($error)
    echo "There were error(s) in your signup details: " . $error;
else {
    $link = mysqli_connect("sql106.byethost.com", "b24_22957102", "dlink5229", "b24_22957102_demo0331");

    if (!$link) {
        echo "Failed.";
    } else {
        $query = "SELECT * FROM `users` WHERE userEmail='$_POST[userEmail])'";
        $result = mysqli_query($link, $query);
        $results = mysqli_num_rows($result);

        if ($results)
            echo "That email address already exists. Do you want to log in? ";
        else {
            $query = "INSERT INTO users (userName, userEmail, userPassword) VALUES(
                '$_POST[userName]','$_POST[userEmail]',md5('$_POST[userPassword]'))";



            mysqli_query($link, $query);
            echo "You've been signed up!";


        }
    }
}
```

} ?&gt; &lt;!DOCTYPE html&gt; Sign Up

