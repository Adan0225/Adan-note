# 6.4.2 Accordion HTML部份

## 範例

&lt;!DOCTYPE html&gt;

網頁代碼播放器  
  
    body{  
      margin: 0;  
      padding: 0;  
      background-color: \#1D1E22;  
    }  
  \#menu{  
    width: 100%;  
    height: 60px;  
    background-color: black;  
    font-family: "Helvetica Neue","Helvetic","Arial";  
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
  
  }  
  
  .button span{  
    transition: all 0.5s;  
  
  
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
  
  
 網頁代碼播放器 運行代碼

* **HTML**
* *   
* * 
* * 

### link

[https://drive.google.com/file/d/1V0LkTuIs1LTWZ62gGFPEAXNNZjaF5jHz/view?usp=sharing](https://drive.google.com/file/d/1V0LkTuIs1LTWZ62gGFPEAXNNZjaF5jHz/view?usp=sharing)

