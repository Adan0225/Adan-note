# 6.4.3 網頁代碼播放器-OK

## 網頁代碼播放器

### 範例

&lt;!DOCTYPE html&gt;

網頁代碼播放器  
  
    body{  
      margin: 0;  
      padding: 0;  
      background-color: \#1D1E22;  
      overflow: hidden;  
    }  
  \#menu{  
    width: 100%;  
    height: 60px;  
    background-color: black;  
    font-family: "Helvetica Neue","Helvetica","Arial";  
  }  
  
  .menu-container {  
    width: 1200px;  
    margin: auto; /\*在中間設定auto\*/  
    padding-top: 15px;  
  
  }  
  \#logo{  
    color: white;  
    float: left;  
    font-size: 1.5em;  
    margin-left: 500px;  
    padding-left: 15px;  
  
  }  
  .button{  
    float: right;  
    font-size: 18px;  
    width: 120px;  
    border: none;  
    border-radius: 4px;  
    padding: 5px;  
    background-color: \#FFDD40;  
  
    cursor: pointer;  
    transition: all 0.5s;  
  
  }  
  
  .button span{  
    transition: 0.5s;  
  
  
  }  
  .button span::after{  
    content: "\00bb";  
    /\* color: white; \*/  
    position: absolute;  
    opacity: 0;  
    right: 0px;  
    transition: 0.5s;  
  }  
  
  .button:hover span {  
    position: relative;  
    padding-right: 25px;  
  
  }  
  .button:hover span::after{  
    opacity: 1;  
    right: 0;  
  }  
  .clear{  
    clear: both;  
  
  }  
  
  \#accordion{  
  
      background-color: \#FFDD40;  
      width: 100%;  
      height: 400px;  
      margin: auto;  
  
      overflow: hidden;  
  
  }  
  \#accordion h3, \#accordion div{  
    display: inline-block;  
    vertical-align: top;  
    text-align: center;  
  }  
  \#accordion h3{  
    background-color: \#36383F;  
    color: white;  
    transform: rotate\(270deg\);  
    width: 400px;  
    height: 30px;  
  
    margin: 185px 0px 0px -170px;  
  
  }  
  \#accordion div{  
    width: 340px;  
    height: 400px;  
  
    margin: 0px 5px 0 -170px;  
  }  
  textarea{  
    width: 100%;  
    height: inherit;  
    resize: none;  
    background-color: inherit;  
    border: none;  
  
    color: \#ddca7e;  
    font-size: 20px;  
  }  
  
  \#result-container{  
    background-color: \#1D1E22;  
    width: 100%;  
  }  
  
  h2{  
    width: 100%;  
    height: 30px;  
    background-color: \#36383F;  
    color: white;  
    margin: 0;  
    text-align: center;  
    font-family: "Helvetica Neue","Helvetica","Arial";  
    font-weight: normal;  
  }  
  
  iframe{  
    border: none;  
    width: 100%;  
    background-color: white;  
  }  
  
  .footer{  
    background-color: \#36383F;  
    width: 100%;  
    height: 40px;  
    position: fixed;  
    bottom: 0;  
    left: 0;  
  }  
  
  
 網頁代碼播放器 運行代碼

* **HTML**
* *      
* *      
* *      

### 結 果

  
  
$\(".code-container"\).hide\(\);  
$\("\#css-code"\).css\("margin-left", "-350px"\);  
$\("\#js-code"\).css\("margin-left", "-350px"\);  
  
var $result = $\("\#result-frame"\);  
var $window = $\(window\).on\("resize", function\(\){  
   var height = $\(this\).height\(\) -530;  
   $result.height\(height\);  
  
}\).trigger\("resize"\);  
  
$\(".tab"\).click\(function\(event\){  
  $\(this\).nextAll\(".tab"\).css\("margin-left", "-170px"\);  
  $\(this\).nextAll\(".code-container"\).animate\(  
  {width:"0px"},  
  {duration: 1500, queue: false}  
\);  
   $\(this\).next\(\).animate\(  
     {  
       backgroundColor:"\#1D1E22",  
     }  
   \);  
  
  var leftOffset = $\(this\).offset\(\).left;  
   // console.log\(leftOffset\);  
  
   if\(leftOffset &gt; 680\){  
     // $\(this\).prevAll\(".tab"\).css\("margin-left","-170px"\);  
     $\(this\).prevAll\(".tab"\).animate\(  
     {  
      marginLeft: "-170px",  
    },  
    {  
      duration: 700, queue: false  
    }  
   \);  
     $\(this\).next\(\).animate\(  
  
       {  
         width:"680px",  
       },  
       {  
         duration: 2000, queue: false  
       }  
     \);  
     $\(this\).prevAll\(".code-container"\).animate\(  
       {  
         width: "0px",  
       },  
       {  
         duration: 1000, queue: false  
       }  
     \);  
  
  
   }else {  
     $\(this\).next\(\).animate\(  
  
       {  
         width:"680px",  
       },  
       {  
         duration: 2000, queue: false  
       }  
     \);  
  
   }  
  
}\);  
  
$\("\#runCode"\).click\(function\(\){  
 $\("\#result-frame"\).contents\(\).find\("head"\).html\("&lt;style&gt;" + $\("textarea\#css-code"\).val\(\) + "&lt;/style&gt;"\);  
 $\("\#result-frame"\).contents\(\).find\("body"\).html\($\("textarea\#html-code"\).val\(\)\);  
  
  document.getElementById\('result-frame'\).contentWindow.eval\($\("textarea\#js-code"\).val\(\)\);  
  
}\);  
  


#### 執行HTML、CSS、JavaScript

 Hello World!

body {

background-color: red;

}

## myText {

color:white;

}

document.getElementById\("myText"\).innerHTML = "It is work!";

#### link

[https://drive.google.com/file/d/10sicUNlPSFPWVd4Y1BY8YylBR0N58-4m/view?usp=sharing](https://drive.google.com/file/d/10sicUNlPSFPWVd4Y1BY8YylBR0N58-4m/view?usp=sharing)

