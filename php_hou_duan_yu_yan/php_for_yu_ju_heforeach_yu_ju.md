# 4.3 PHP For 語句和 Foreach語句

## 範例

1. &lt;?php

   for\($i = 1; $i &lt;=10; $i=$i+2\){

   ```text
   echo $i."<br/>";
   ```

   } ?&gt;

2.

&lt;?php

for\($i = 10; $i&gt;0; $i=$i-1\){

```text
   echo $i."<br/>";
 }
```

?&gt;

3 &lt;?php

$myArray = array\("cat","dog","fish"\);

foreach\($myArray as $key =&gt; $value\){

```text
 echo "位置:$key,值為:$value<br/>";

}
```

?&gt;

