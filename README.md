# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column     | Type          | Options     |
| ---------- | ------------- | ----------- |
| title      | string        | null: false |
| catch_copy | text          | null: false |
| concept    | text          | null: false |
| user       | references    |             |

### Association

- has_many   :comments
- belongs_to :users

## commentsテーブル

| Column    | Type   | Options     |
| --------- | ------ | ----------- |
| text      | string | null: false |
| user      | string | null: false |
| prototype | string | null: false |

### Association

- belongs_to :users
- belongs_to :users