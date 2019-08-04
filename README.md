## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false| 
### Association
- has_many :messages
- has_many :users, through: :groups
- has_many :members

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|group_members|integer|null: false, foreign_key: true|
### Association
- has_many:users, through: :members
- has_many:members
- has_many :messages

##messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group


##membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many: users