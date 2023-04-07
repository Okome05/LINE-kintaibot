# LINEBotで研究時間を管理
LINEBotのMessagingAPIを使って研究開始と研究終了を記録し，一日の研究時間とこれまでの累計時間を記録する．


## LINEBot×Python×Raspberry Pi×ngrokを使って実装を行う
### LINEBotの作成
#### ビジネスアカウントを作成する
[LINE Developers](https://developers.line.biz/ja/services/messaging-api/)からログインを押し画像の画面が表示されたらビジネスアカウントを作成する
![スクリーンショット 2023-04-07 182441](https://user-images.githubusercontent.com/130141399/230583693-8baeb486-9372-418f-9d76-e6fbb0668512.png)
#### 新規チャンネルの作成
新規でMessaging APIのチャンネルを新規作成する
![スクリーンショット 2023-04-07 185051](https://user-images.githubusercontent.com/130141399/230587893-362e5352-c44f-4a03-a34c-60be49c27417.png)
この先は指示に従って作成してください
#### 必要情報の確認　（この後認証のために使用する）
##### Basic settingの項目から Channel secretの情報取得（黄色で塗りつぶした部分をコピーしておく）
![スクリーンショット 2023-04-07 190423](https://user-images.githubusercontent.com/130141399/230590256-a0fb51cc-a4fd-4c5a-bd82-90bfd5647865.png)
##### MessagingAPIの項目から　Channel access tokenの情報を取得（黄色で塗りつぶした部分をコピーしておく）
![スクリーンショット 2023-04-07 190740](https://user-images.githubusercontent.com/130141399/230590813-c03c9b08-683e-4703-858d-df475ad6ed6f.png)

###  Pythonでコードを書く
#### PythonSDKを参考に実際に書いてみる！
[line-bot-sdk-python](https://github.com/line/line-bot-sdk-python)のgithubを参考にさせていただきました．  
そのままコピペしてそこに追加していく形で作成  


### Raspberry Piの設定
#### 

