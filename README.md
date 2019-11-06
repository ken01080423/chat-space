#chatSpace DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|user_name|string|null: false|
### Association
- has_many :posts
- has_many :groupe_users
- has_many :groups, through: :groups_users

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|tweet|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- belongs_to :groups

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
### Association
- has_many :posts
- has_many :groups_users
- has_many :users, through :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- belongs_to :groups
