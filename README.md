# テーブル設計

## usersテーブル

|column    |Type  |options    |
|----------|------|-----------|
|email     |string|null: false|
|password  |string|null: false|
|name      |string|null: false|
|profile   |text  |null: false|
|occupation|text  |null: false|
|position  |text  |null: false|

### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル

|column    |Type      |options    |
|----------|----------|-----------|
|title     |string    |null: false|
|catch_copy|text      |null: false|
|concept   |text      |null: false|
|image     |          |           |
|user      |references|           |

### Association

- belongs_to :user
- has_many   :comments

## commentsテーブル

|column    |Type      |options    |
|----------|----------|-----------|
|text      |text      |null: false|
|user      |references|           |
|prototype |references|           |

### Association

- belongs_to :user
- belongs_to :prototype
