## groupsテーブル
|column|Type|Options|
|------|----|-------|
|name|string|null: false|

## Association
has_many :users, through: :groups_users
has_many :messages
has_many :groups_users

## usersテーブル
|column|Type|Options|
|------|----|-------|
|Email|string|null:false|
|password|string|null: false|
|nickname|string|null: false|

## Association
has_many :groups, through: :groups_users
has_many :messages
has_many :groups_users

## Messagesテーブル
|column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user