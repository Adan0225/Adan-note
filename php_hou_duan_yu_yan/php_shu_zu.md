# 4.1PHP 數組

## 範例

數組 用print\_r 輸出

&lt;?php

$myArray = array\("漢 堡 包", "巧 克 力", "咖 啡"\); //echo $myArray; print\_r\($myArray\);

echo "  
  
"; echo $myArray\[2\]; echo "繼續運行"; echo"  
  
";

$anotherArray\[0\] = "冰 淇 淋"; $anotherArray\[1\] = "牛 奶";

print\_r\($anotherArray\);

echo "  
  
";

$thirdArray = array\(

"法國"=&gt; "法語", "美國"=&gt; "英語", "日本"=&gt; "日語" \); print\_r\($thirdArray\); echo "  
  
"; echo $thirdArray\["美國"\]; print\_r\($thirdArray\);

echo "  
  
"; $anotherArray\[\] ="沙 拉"; print\_r\($anotherArray\);

echo "  
  
";

unset\($thirdArray\["美國"\]\);

print\_r\($thirdArray\);

echo "  
  
";

$name = "Adan";

unset\($name\); echo $name;

?&gt;

