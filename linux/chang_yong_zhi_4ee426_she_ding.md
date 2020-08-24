# 12.1 常用指令&設定

## ~/.bashrc  環境變數

* which xxx // 查看 xxx 路徑
* find . -name '\*.py' \| xargs ag 'keyword'
* ls -lart // 檔案舊-&gt;新排序
* z  資料夾關鍵字 // 快速切換
* crtl + r 歷史紀錄
* ctrl + l 清畫面
* ctrl + a // 遊標最前面
* ctrl + e // 遊標最後面

## github 砍某帳號所有 repo

* ex ywchiu

```bash
curl -s https://api.github.com/users/ywchiu/repos?per_page=200 | python -c $'import json, sys, os\nfor repo in json.load(sys.stdin): os.system("git clone " + repo["git_url"])'
```

