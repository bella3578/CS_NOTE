# CS_NOTE
**Linux-絕對/相對路徑的移動**
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

**Linux介紹指令及實做-編輯文檔**
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

**Linux背景知識-使用者與群組**
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
 
**Linux背景知識-資料傳輸**
- 當瀏覽器輸入網址，發出一個 GET 請求時，過程中發生了哪些事情？
1. TCP三向交握
   - 在瀏覽器送出請求之後，瀏覽器和伺服器就會開始初步溝通，確定雙方的溝通管道順暢，以便後續請求的執行
2. 瀏覽器請求、資料傳輸、渲染畫面
   - 如同前面所提，當三項交握結束後，瀏覽器和伺服器便會開始執行請求、資料傳輸與渲染畫面的過程
3. TCP四次揮手，結束連線
   - 在網頁成功渲染之後，瀏覽器就會和伺服器進行最後的溝通，確認傳輸過程已完成，準備結束連線         

#Linux背景知識-檔案系統管理

![image](https://user-images.githubusercontent.com/91451864/143672638-750a9bff-e18a-4fb7-9220-b2445f1f5c1e.png)

**Linux介紹指令及實做-更改使用者權限**


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

**ls -l可查看每個檔案與目錄的擁有者與群組**
![image](https://user-images.githubusercontent.com/91451864/143673922-c798ed5a-36d6-4718-ac9e-fc0701854429.png)

**chown可修改檔案或目錄擁有者及群組**
![image](https://user-images.githubusercontent.com/91451864/143673933-f12dea27-cfd2-418e-8d8e-f7d7873ce0fe.png)


**Linux介紹指令及實做-壓縮檔案**
- gzip
    - 壓縮：gzip FileName
    - 解壓縮：
      - gunzip FileName.gz
      - gzip-d FileName.gz
- xz
    - 壓縮：xz -z FileName
    - 解壓縮：xz -d FileName.xz
- tar.gz
    - 壓縮：tar -zcvf FileName.tar.gz DirName
    - 解壓縮：tar -zxvf FileName.tar.gz
    
**Linux介紹指令及實做-檔案搜尋**
- find [path] [option] [action] filename
    - option
      - size EX：找出大於500M的檔案→-size +500M
      - name EX：找出為照片的檔案→-name "*.jpg"
      - type EX：-type f→一般檔案;-type d→一般目錄
      - user EX：同時找兩個擁有者的檔案→-user user1 -o -user user2
    - action -exec
      - ls
      - print
- which filename
    - n<文件名长度>指定文件名長度，指定的長度必須大於或等於所有文件中最長的文件名。
    - p<文件名長度>與-n参數相同，但此處的<文件名長度>包括了文件的路徑。
    - w指定輸出欄位的寬度。
    - V顯示版本訊息。

**Linux介紹指令及實做-檔案內容查閱**
- cat  從第一行顯示檔案內容、形成新檔案
    - cat -n file1 > file2→把file1的檔案內容加上行號後輸入file2檔案
      - n→由1開始對所有輸出的行數編號
      - (>)→將多個文件覆蓋到目標文件中
      - (>>)→將多個文件追加到目標文件中
- tac  從最後一行開始顯示
     - tac -r -s 'x\|[^x]' test.log→一個接著一個字符的反轉一個文件
       - -r→將分隔符作為基礎正規表達是處理
       - -s→使用String作為分隔符代替默認的換行符
- more 一頁一頁的顯示檔案內容
     - more +20 testfile→從第20行開始顯示testfile的文檔內容
       - ENTER：向下n行(default為1行)
       - Ctrl+F/SPACE：向下滾動一屏
       - Ctrl+B：返回上一屏
- less 與 more 類似，顯示檔案室允許用戶既可以向前又可以向後翻頁閱讀檔案
     - ps -ef |less→ps查看進程信息並通過less分頁顯示	
       - j→下一行
       - k→上一行
       - G→移動到最後一行
       - g→移動到第一行
- head/tail 只看頭/尾巴幾行
     - head -n 20 state.txt | tail -10→顯示11~20行的內容

**Linux介紹指令及實做-網路相關**
- 影響網路速度的因素：
     - 延遲（Latency）：封包從來源端至目的端中間所花的時間
     - 頻寬（Bandwidth）：傳輸媒介的最大吞吐量
- 網路延遲（Latency）的組成元素:
     - propagation delay：封包在網路線上傳輸所花費的時間，與網路線上電子訊號跑的速度有關，這個時間就是距離除以訊號傳送速度所得到的數值。
     - transmission delay：網路卡將資料傳送到網路線上所花的時間，與網路設備的傳送速度有關。
     - nodal processing delay：路由器處理封包表頭、檢查位元資料錯誤與尋找配送路徑等所花費的時間。
     - queuing delay：路由器因為某些因素無法立刻將封包傳送到網路上，造成封包暫存在佇列中等待的時間。
- nrtstat
     - 查看端口是否被占用：netstat -a|grep 3306
     - 查看數據包統計信息：netstat -s
     - 查看路由信息：netstat -r

