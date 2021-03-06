## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true,index: true|
|email|string|null: false, unique: true|
|password|string|null: false|

### Association
- has_many :user_groups
- has_many :groups, through: :user_groups
- has_many :messeages

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|

### Association
- has_many :user_groups
- has_many :users, through: :user_groups
- has_many :messeages

## user_groups中間テーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
|body|text||
|image|string||

### Association
- belongs_to :user
- belongs_to :group
