# 6.4.3 Accordion CSS

## Accordion CSS

### 範例

&lt;!DOCTYPE html&gt;

 網頁代碼播放器

```text
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />

 <link rel="stylesheet" href="https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/themes/smoothness/jquery-ui.css">
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js"></script>
```

```text
body{
  margin: 0;
  padding: 0;
  background-color: #1D1E22;
}
```

## menu{

```text
width: 100%;
height: 60px;
background-color: black;
font-family: "Helvetica Neue","Helvetic","Arial";
```

}

.menu-container { width: 1200px; margin: auto; /_在中間設定auto_/ padding-top: 15px;

}

## logo{

```text
color: white;
float: left;
font-size: 1.5em;
margin-left: 500px;
padding-left: 15px;
```

} .button{ float: right; font-size: 18px; width: 120px; border: none; border-radius: 4px; padding: 5px; background-color: \#FFDD40; cursor: pointer;

}

.button span{ transition: all 0.5s;

} .button span::after{ content: "\00bb"; / _color: white;_ / position: absolute; opacity: 0; right: 0px; transition: 0.5s; }

.button:hover span { position: relative; padding-right: 25px;

} .button:hover span::after{ opacity: 1; right: 0; } .clear{ clear: both;

}

## accordion{

```text
  background-color: #FFDD40;
  width: 100%;
  height: 400px;
  margin: auto;

  /* overflow: hidden; */
```

}

## accordion h3, \#accordion div{

```text
display: inline-block;
vertical-align: top;
text-align: center;
```

}

## accordion h3{

```text
background-color: #36383F;
color: white;
transform: rotate(270deg);
width: 400px;
height: 30px;
margin:185px 0px 0px -170px;
```

}

## accordion div{

```text
width: 340px;
height: 400px;
margin: 0px 5px 0 -170px;
```

} textarea{ width: 100%; height: inherit; resize: none; background-color: inherit; border: none;

```text
color: #ddca7e;
font-size: 20px;
```

}

&lt;/style&gt; &lt;/head&gt;

    網頁代碼播放器

```text
  </div>
  <button id="runCode" class="button" type="button" name="button"><span>運行代碼</span></button>
```

&lt;/div&gt;

&lt;/div&gt;

* **HTML**
* *   
* * 

Javascript

&lt;/ul&gt;

&lt;/body&gt; &lt;/html&gt;

#### link

[https://drive.google.com/file/d/1G0dNas2du8QazU7ay8MfXAOCuRtGbBtn/view?usp=sharing](https://drive.google.com/file/d/1G0dNas2du8QazU7ay8MfXAOCuRtGbBtn/view?usp=sharing)

