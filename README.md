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

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false,unique: true|
|password|string|null: false|
|nickname|string|null: false,unique: true|

### Association
- has_many :groups_users
- has_many :groups
- has_many :comments
- has_many :images

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false|
|group_name|integer|null: false|

### Association
- has_many :groups_users
- has_many :users

## imagesテーブル

|Column|Type|Options|
|------|----|-------|
|image|text||
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text||
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :users