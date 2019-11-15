# データベースの設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name     |string|null: false, uniqueness: true, add_index :users|
|email    |string|null: false, uniqueness: true, add_index :users|
|password |string|null: false, add_index :users                  |

### Association
- has_many :groups, through :members
- has_many :members
- has_many :messages


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|

### Association
- has_many :users, through :members
- has_many :members
- has_many :messages


## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id |references :user |foreign_key: true|
|group_id|references :group|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body    |text             | 
|image   |string           |
|user_id |references :user |foreign_key: true|
|group_id|references :group|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

