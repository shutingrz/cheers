# Cheers!
Cheers!はプログラミングの勉強のために作ったSNSです。  
指定ユーザに対してのイイネ！の送信や、メッセージを含んだイイネ！の送信が可能です。  
ただしイイネ！の送信は API のみで可能です。  

現時点においてAPIと画面を同時に利用するとセキュリティ上のリスクが懸念されます（XSSなど)。  

# Install
## 推奨環境
* Python 3.6 以上
* MySQL 5.6 以上

## ライブラリのインストール
```
pip install -r ./requirements.txt
```

## データベースの作成
好きな名前で作ってください。「cheers」とか。

## テーブルの作成
bin/cheers/db/sql ディレクトリ以下の .sql ファイルを用いてテーブルを作成してください。  
```
mysql -u [user] -p cheers < authentication.sql
mysql -u [user] -p cheers < gift_transaction.sql
mysql -u [user] -p cheers < profile.sql
mysql -u [user] -p cheers < user_hash.sql
mysql -u [user] -p cheers < user.sql
```

## コンフィグファイルの設定
bin/cheers.conf で下記項目を設定してください。
* LISTEN  
リッスンするアドレス
* PORT  
リッスンするポート番号
* DBURL  
データベースの接続先URL

以下は任意項目です。

* MAX_USERID_LENGTH  
ユーザIDの最大長
* MAX_USERPASS_LENGTH  
パスワードの最大長
* DEFAULT_STOCK_VALUE  
新規ユーザ作成時のイイネ！残高の初期数
* DEBUG_MODE  
デバッグモードのオンオフ  
現時点ではオンでユーザ削除機能が有効化されます
* INFINITE_MODE  
イイネ！をしても残高が減らないようにする

# Startup
```
cd bin
./app.py
```


# VERSION
* 0.0.1  
初回テストリリース

# LICENSE
MIT License
