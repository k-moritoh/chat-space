# chat-space

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|foreign_key: true|
|body|text||
|image|string||

### Association
belongs_to :group
belongs_to :user



## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|name|string|null: false, foreign_key: true|

### Association
belongs_to :groups
belongs_to :messages



## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|

### Association
has many :messages
belongs_to :users



## 中間テーブル
## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
belongs_to :group
belongs_to :user
