# README
# 説明書

### Ruby version
### Rubyバージョン
- ruby 2.5.1p57
- rails 5.0.7.2


### System dependencies
### システムの依存関係

### Configuration
### 設定

### * Database creation
### * データベース作成

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_name|string|null: false, unique: true, add_index :users|
|email|string|null: false, unique: true, add_index :users|
|password|string|null: false, add_index :users|

### Association
- has_many :groups, through:members
- has_many :members
- has_many :messages


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|

### Association
- has_many :users, through:members
- has_many :members
- has_many :messages


## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references :user|foreign_key: true|
|group_id|references :group|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|references :user|foreign_key: true|
|group_id|references :group|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


### Database initialization
### データベースの初期化

### How to run the test suite
### テストスイートの実行方法

### Services (job queues, cache servers, search engines, etc.)
### サービス（ジョブキュー、キャッシュサーバー、検索エンジンなど）

### Deployment instructions
### 展開手順

### ...
