# 6.2分頁和排序功能

## 範例 基本架構 autcomplete

&lt;!DOCTYPE html&gt;

Learning jQuery UI  
  
  
 請輸入您的內容:   
  
$\(function\(\) {  
  var availableTags = \[    //autocomplete 功能，輸入關鍵字即會自動跑出  
    "ActionScript",  
    "AppleScript",  
    "Asp",  
    "BASIC",  
    "C",  
    "C++",  
    "Clojure",  
    "COBOL",  
    "ClodFusion",  
    "Erlang",  
    "Fortran",  
    "Groovy",  
    "Haskell",  
    "Java",  
    "Javascript",  
    "Lisp",  
    "Perl",  
    "PHP",  
    "Python",  
    "Ruby",  
    "Scala",  
    "Scheme"  
  
  \];  
  
  $\("\#tags"\).autocomplete\({  
    source: availableTags  
  
  }\);  
}\);  
  


