# CS_NOTE
#Linux-絕對/相對路徑的移動
絕對路徑 | 相對路徑
------------- | -------------
路徑的寫法『一定由根目錄 / 寫起|相對路徑意指『相對於目前工作目錄的路徑』,寫法『不是由 / 寫起』
例如： /usr/share/doc  |由 /usr/share/doc 到 /usr/share/man 底下時，寫成： 『cd ../man』

- cp 複製
- mv 移動
- cd 變換目錄
- cat 查看檔案內容
- pwd 顯示目前的目錄
- mkdir 建立一個新目錄
- rmdir 刪除一個裡面是空的空目錄-
- ls 顯示目錄下的所有內容

#Linux介紹指令及實做-編輯文檔
1. nano
   - Ctrl C：顯示游標所在
   - Ctrl W：查詢命令，按下後會跳轉到末行的反白位置，輸入要查詢的內容在回轉即可
2. vi/vim(vim相當於vi的升級版)
   - 一般模式：可使用上下左右進行游標 宜動、刪除字元及複製貼上檔案資料
   - 編輯模式：編輯文字:i鍵即可進入編輯模式,Esc鍵退出編輯模式
   - 命令列模式 : 
      1.  :w將編輯的資料寫入硬碟檔案中
      2.  :w!若檔案 屬性為『只讀』時，強制寫入該檔
      3.  :wq儲存後離開(若為:wq!則為強制儲存後離開)
      4.  :w[ filename ]將編輯的資料儲存成另一個檔案（類似另存新檔）
      5.  :q離開
      6.  :q!強制離開不儲存檔案
      8.    :r[ filename ]在編輯的資料中，讀入另一個檔案的資料
      9.   :set nu顯示行號，設定後會在每一列的自首顯示該列的行號

#Linux背景知識-使用者與群組
- 關於身份:
     - 身份分類：
          - user(onwer)
          - group
          - others
     - 群組 (group) 的主要用意：
          - 將帳號歸類，有助於類似專案開發
          - 每個使用者均可加入 多個群組。
 - 關於身份類別：
     - 系統管理員： root
     - 一般帳號：
          - 系統帳號 (用於系統帳號的工作)
          - 一般使用者帳號 (用於一般使用者登入用。)

![image](https://user-images.githubusercontent.com/91451864/143672598-cef2652a-9aa0-4f30-adef-dbbb6251cd71.png)
#Linux背景知識-檔案系統管理

![image](https://user-images.githubusercontent.com/91451864/143672638-750a9bff-e18a-4fb7-9220-b2445f1f5c1e.png)

#Linux介紹指令及實做-更改使用者權限


- 檔案 file1.txt 設為所有人皆可讀取 :
     - chmod ugo+r file1.txt
- 將檔案 file1.txt 與 file2.txt 設為該檔案擁有者，與其所屬同一個群體者可寫入，但其他以外的人則不可寫入 :
     - chmod ug+w,o-w file1.txt file2.txt
- 將 ex1.py 設定為只有該檔案擁有者可以執行 :
     - chmod u+x ex1.py
- 將目前目錄下的所有檔案與子目錄皆設為任何人可讀取 :
     - chmod -R a+r *
- chmod a=rwx file == chmod 777 file
- chmod ug=rwx,o=x file ==  chmod 771 file
- chmod可控制檔案如何被他人調用
     - → chmod [-cfvR] [--help] [--version] mode file…
- mode許可權設定字串 
     - → [ugoa...][[+-=][rwxX]...][,...]

![image](https://user-images.githubusercontent.com/91451864/143673709-6a24df4f-139e-4a80-9356-003f8ba8b003.png)
![image](https://user-images.githubusercontent.com/91451864/143673751-ed8a50c9-5700-4a2d-ad28-8d60fa362310.png)
![image](https://user-images.githubusercontent.com/91451864/143673644-cca9b002-7665-43b2-bcd7-8f995f938cf7.png)

