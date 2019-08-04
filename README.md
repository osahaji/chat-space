## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :groups, through: :members
- has_many :members
- has_many :messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|integer|null: false, foreign_key: true|
|group_members|integer|null: false|
### Association
- has_many:users,through: :members
- has_many:members
- has_many :messages

##messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group

##membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|refereces|null: false, foreign_key: true|
|group_id|refereces|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


