# 13.1Git and Github version control

## Git and Github version control

Git 與 Github 版本控制基本指令與操作入門教學

### 什麼是版本控制系統（Version Control System）？

![](https://blog.techbridge.cc/img/kdchang/cs101/files.png)

版本控制系統是一種軟體工程的開發技巧，可以透過這個系統讓每位成員的軟體版本可以方便同步和維護管理（不然要用 email 或是其他工具傳送和管理十分麻煩，尤其程式又常常會有不同版本修改的問題！）。在沒有版本控制系統時，我們常會在編輯檔案前複製一個備份，或是在更新檔案後產生許多重複檔案，非常不便且難以維護。因此，使用版本控制系統的需求就應運而生啦！

一般在軟體開發中又分為中央式系統（例如：Subversion、CVS 等）與分散式系統（例如：Git、BitKeeper、mercurial 等），中央式版本控制系統的工作主要在一個伺服器進行，由中央管理存取權限「鎖上」檔案庫中的檔案，一次只能讓一個開發者進行工作。而分散式系統讓不同開發者直接在各自的本地檔案庫工作，並容許多個開發者同時更動同一個檔案，而每個檔案庫有另外一個合併各個改變的功能。分散式系統讓開發者能在沒有網路的情況下也能繼續工作，也讓開發者有充分的版本控制能力，而不需經中央管理者的許可，但分散式系統仍然可以有檔案上鎖功能。

### 什麼是 Git？什麼是 Github？

Git 是一個分散式版本控制軟體，最初由 Linus Torvalds 創作（也是作業系統 Linux 系統的開發者），其最初目的是為更好地管理 Linux kernel 開發而設計，其具備優秀的 merge tracing 合併程式碼的能力（使用程式碼 snapshot 來比較歷史版本差異）。

Github 則是一個支援 git 程式碼存取和遠端托管的平台服務，有許多的開放原始碼的專案都是使用 Github 進行程式碼的管理。若是讀者未來有志於從事程式設計相關工作的話，建議可以熟悉掌握 Git 和 Github 的使用，並建立自己的 Github profile 作品集。

### Git 基本觀念

![](https://blog.techbridge.cc/img/kdchang/cs101/git-workflow.png)

Git 可以分為 Local（本地）和 Remote（遠端）兩個環境，由於 Git 屬於分散式的版本控制系統，所以開發者可以在離線 local 環境下開發，等到有網路時再將自己的程式推到 Remote 環境或 pull 下其他開發者程式碼進行整合。在 Local 中我們又分為 working directory（工作資料夾）、staging area（暫存區）和 repositories（檔案庫）。

當自己開發時會在工作資料夾工作，當要進入檔案庫之前會先將檔案加入暫存區，確認沒問題則 commit 到檔案庫中，最後 push 上去 remote 環境。在 Git 中若是有和其他開發者一起合作，則會需要處理不同 branch 之間 conflict 和 merge 的問題。

![](https://blog.techbridge.cc/img/kdchang/cs101/git-branch.png)

## Git 安裝教學

[https://blog.techbridge.cc/2018/01/17/learning-programming-and-coding-with-python-git-and-github-tutorial/](https://blog.techbridge.cc/2018/01/17/learning-programming-and-coding-with-python-git-and-github-tutorial/)

