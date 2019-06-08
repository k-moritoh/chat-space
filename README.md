# chat-space

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|body|text||
|image|string||

### Association
belongs_to :group
belongs_to :user



## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|

### Association
has many :groups, through: :members
has many :messages
has_many :members


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
has many :messages
has many :users, through: :members
has_many :members


## 中間テーブル
## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
belongs_to :group
belongs_to :user