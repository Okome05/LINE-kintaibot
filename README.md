# LINEBotで研究時間を管理
LINEBotのMessagingAPIを使って研究開始と研究終了を記録し，一日の研究時間とこれまでの累計時間を記録する．
### LINEBot×Python×Raspberry Pi×ngrokを使って実装を行う
![Screenshot_20230407-195847](https://user-images.githubusercontent.com/130141399/230598056-f77d095f-1845-434e-90e2-8289858d7b01.png)

## LINEBotの作成
### ビジネスアカウントを作成する
[LINE Developers](https://developers.line.biz/ja/services/messaging-api/)からログインを押し画像の画面が表示されたらビジネスアカウントを作成する
![スクリーンショット 2023-04-07 182441](https://user-images.githubusercontent.com/130141399/230583693-8baeb486-9372-418f-9d76-e6fbb0668512.png)
### 新規チャンネルの作成
新規でMessaging APIのチャンネルを新規作成する
![スクリーンショット 2023-04-07 185051](https://user-images.githubusercontent.com/130141399/230587893-362e5352-c44f-4a03-a34c-60be49c27417.png)
この先は指示に従って作成してください
### 必要情報の確認　（この後認証のために使用する）
#### Basic settingの項目から Channel secretの情報取得（黄色で塗りつぶした部分をコピーしておく）
![スクリーンショット 2023-04-07 190423](https://user-images.githubusercontent.com/130141399/230590256-a0fb51cc-a4fd-4c5a-bd82-90bfd5647865.png)
##### MessagingAPIの項目から　Channel access tokenの情報を取得（黄色で塗りつぶした部分をコピーしておく）
![スクリーンショット 2023-04-07 190740](https://user-images.githubusercontent.com/130141399/230590813-c03c9b08-683e-4703-858d-df475ad6ed6f.png)

##  Pythonでコードを書く
### PythonSDKを参考に実際に書いてみる！
[line-bot-sdk-python](https://github.com/line/line-bot-sdk-python)のgithubを参考にさせていただきました．  
そのままコピペしてそこに追加していく形で作成  

#### 今回はCSVファイルに情報を書き加えていくことにする

### 新規アクセスしたユーザーにはファイルを新規作成する
関数内の処理内容としてはパス内にLineのユーザーIDを含んだファイルが存在するか確認し，ない場合は新規作成・ある場合は何も行わない
![スクリーンショット 2023-04-07 193628](https://user-images.githubusercontent.com/130141399/230594918-89d92fb9-2c0f-4dc8-8349-fbd40814ea61.png)

### 研究を開始したときの処理関数
開始処理を行ったときの時刻をdatetime.nowで取得し，対象のセル位置に打刻する  
連続で開始処理が行われると正常に動かないので条件分岐をつけている
![スクリーンショット 2023-04-07 194115](https://user-images.githubusercontent.com/130141399/230595271-06ee964d-1f6f-4b5b-af4d-0c643b817807.png)
global start_time　メッセージの返信に使用するのでグローバル変数としている

### 研究を終了したときの処理関数
終了処理を行ったときの時刻をdatetime.nowで取得し，対象のセル位置に打刻する  
開始時刻と終了時刻から１日の研究時間の算出，前回の累積時間から新たな合計研究時間を算出し，対象のセル位置に打刻を行う
![スクリーンショット 2023-04-07 194422](https://user-images.githubusercontent.com/130141399/230595701-13513236-b8a5-4942-a81c-295bb88350de.png)
global end_time,Research_time,total_time　これらはメッセージの返信に使用するのでグローバル変数としている

### LINEBotに関する設定部分
この部分に先ほどコピーしたIDなどを入力する  
![スクリーンショット 2023-04-07 193215](https://user-images.githubusercontent.com/130141399/230597376-9e29a18a-b8ad-410b-b1a5-3e59ad9aa620.png)

### 指定のメッセージを受け取ったときの処理
ここではメッセージを受け取った際にプロフィール情報を取得している
画像のように研究開始！と研究終了！のメッセージに対して記録や返信を行うように設定している
![スクリーンショット 2023-04-07 195416](https://user-images.githubusercontent.com/130141399/230597132-8b56c3b5-988f-4814-bfa7-72a427e37493.png)

## Raspberry Piの設定
### 






























