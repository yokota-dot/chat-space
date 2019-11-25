<!-- Chatspace DB設計 -->
## usersテーブル
|Column|Type|Option|
|------|----|------|
|id|string|null: false|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :groups
- has_many :comments

## groupsテーブル
|Column|Type|Option|
|------|----|------|
|id|string|null: false|
|groupnname|string|null: false|
|user_id|string|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :comments

## massagesテーブル
|Column|Type|Option|
|------|----|------|
|user_id|string|null: false, foreign_key: true|
|image|text||
|text|text||
|group_id|string|null: false, foreign_key: true|
### Association
- belong_to :user
- belong_to :group 