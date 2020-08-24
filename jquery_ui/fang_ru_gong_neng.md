# 6.1放入功能

## 範例

&lt;!DOCTYPE html&gt;

Learning jQuery UI  
\#square {  
  width: 200px;  
  height: 200px;  
  background-color: \#E86D5E;  
}  
  
\#resizable {  
  width: 300px;  
  height: 300px;  
  background-color: \#A68ED1;  
  margin-top: 15px;  
  
}  
  
  
  
   $\("\#square"\).draggable\(\);  
    // $\("\#resizable"\).resizable\(\); //要將resizable make起來，才不會讓正方形一直在上方  
    $\("\#resizable"\).droppable\({  
      drop: function\(event, ui\){  
        // alert\("已經拖入正方形"\);  
        $\(this\).addClass\("ui-state-highlight"\);  
      }  
    }\);  
  


### link

[https://drive.google.com/file/d/1vNj5YcXSAPgCjU6IeP2c4ichvpN7XJvF/view?usp=sharing](https://drive.google.com/file/d/1vNj5YcXSAPgCjU6IeP2c4ichvpN7XJvF/view?usp=sharing)

