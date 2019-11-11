# README

##group_usersテーブル

|Colunm|Type|Options|
|------|----|-------|
|user_id|bigint|null:false,foreign_key: true|
|group_id|bigint|null:false,foreign_key: true|

## Association
- belongs_to: group
- belongs_to: user


##usersテーブル
|Colunm|Type|Options|
|------|----|-------|
|nickname|string|null:false|
|email|string|null:false|
|password|string|null:false|

## Association
- has_many: groups
- has_many: users
- has_many: group_users



##groupsテーブル
|Colunm|Type|Options|
|------|----|-------|
|groupname|string|null:false|

## Association
- has_many: users,through: :groups_users
- has_many: messages
- has_many: group_users



##messagesテーブル
|Colunm|Type|Options|
|------|----|-------|
|text|text|null:false|
|title|string|null:false|
|image|string|
|group_id|string|


## Association
- has_many: users
- has_many: messages