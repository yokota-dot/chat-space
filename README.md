<!-- Chatspace DB設計 -->
## usersテーブル
|Column|Type|Option|
|------|----|------|
|id|string|null: false|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :groups, through: :group_users
- has_many :comments

## group_usersテーブル
|Column|Type|Option|
|------|----|------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
belong_to :user
belong_to :
## groupsテーブル
|Column|Type|Option|
|------|----|------|
|id|string|null: false|
|groupnname|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- has_many :users, through: :group_users
- has_many :comments

## massagesテーブル
|Column|Type|Option|
|------|----|------|
|user_id|string|null: false, foreign_key: true|
|image|text||
|text|text||
|group_id|integer|null: false, foreign_key: true|
### Association
- belong_to :user
- belong_to :group 