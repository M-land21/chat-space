# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

+## userテーブル

|Colum|Type|Options|
|-----|----|-------|
|id|integer|null: false|
|name|text|null: false|
|mail|text|null: false, unique: true|

### Association
-has_many :messages 
-has_many :groups 


## groupテーブル

|Colum|Type|Options|
|-----|----|-------|
|id|integer|null: false|
|name|text|null: false|

### Association
-has_many :users 
-has_many :messages 


## messageテーブル

|Colum|Type|Options|
|-----|----|-------|
|body|text|null: false|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
-belongs_to :users
-belongs_to :groups 



## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user