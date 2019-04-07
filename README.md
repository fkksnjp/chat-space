## membersテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false, unique: true|
|email|text|null: false, unique: true|

### Association
- has_many :members_groups
- has_many :message
- has_many :groups, through: members_groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|text|null: false, unique: true|

### Association
- has_many :members_groups
- has_many :message
- has_many :members, through: members_groups

## members_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :member

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :member
