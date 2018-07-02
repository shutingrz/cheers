ver. 2018/07/02

# API 機能一覧
ほとんどの機能は本番運用を想定していません。  
本機能を生かしたまま運用するとセキュリティ上のリスクが懸念されます。

## ユーザ汎用機能
### ユーザ一覧
```
GET /list
```

### ユーザログイン
```
GET /login?user_id=[user_id]&password=[password]
```
- user_id  
(必須) ユーザID
- password  
(必須) パスワード

### ユーザ登録
```
GET /register?user_id=[user_id]&password=[password]
```
- user_id  
(必須) ユーザID
- password  
(必須) パスワード


### ユーザ削除(管理用)
※ユーザ削除機能の実装後、本機能は削除されます。
```
GET /admin/user/delete/<user_id>
```
- user_id  
(必須) ユーザID  

### ユーザ名の重複確認
```
GET /user/<user_id>/isexist
```
- user_id  
(必須) ユーザID  

### ユーザのプロフィール取得
```
GET /user/<user_id>
```
- user_id  
(必須) ユーザID  

## アカウント機能 (ログイン必要)

### アカウントのイイネ残高と受信数の確認  
```
GET /account/status
```

### 本人から見たプロフィール表示
```
GET /account/profile
```

### プロフィール保存
```
GET /account/profile/save?nickname=[nickname]&email=[email]&department=[department]&introduction=[introduction]
```
- nickname  
(任意) ニックネーム
- email  
(任意) Eメール
- department  
(任意) 所属
- introduction  
(任意) 自己紹介

### イイネ！送信
```
GET /gift?destination=[user_id]&message=[message]
```
- user_id  
(必須) 送信先のユーザID

- message  
(任意) メッセージ


### 受信および送信したイイネ！の一覧表示
```
GET /gifts
```

### 送信したイイネ！の一覧表示
```
GET /gifts/send
```

### 受信したイイネ！の一覧表示
```
GET /gifts/receive
```

# 画面機能一覧
現時点において、API機能を併用した場合のセキュリティの考慮はされていません。

## ユーザ汎用機能

### ログイン画面表示
```
GET /login
```

### ログイン
```
POST /login
```
- user_id  
(必須) ユーザID
- password  
(必須) パスワード

### ログアウト
```
GET /logout
```

### ユーザ一覧表示
```
GET /list
```

### ユーザ詳細表示 (未完成)
```
GET /user/<user_id>
```
- user_id 
(必須) ユーザID

