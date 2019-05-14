# データベース設計

## usersテーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

### Association
- has_many :groups
- has_many :messages


## groupsテーブル

| Column     | Type    | Options     |
| ---------- | ------- | ----------- |
| name       | string  | null: false |

## messagesテーブル

| Column     | Type    | Options                         |
| ---------- | ------- | ------------------------------- |
| body       | text    |                     |
| image      | text    |                                 |
| user_id    | integer | null: false, foreign_key: true  |
| group_id   | integer | null: false , foreign_key: true |
| created_at | daytime | null: false                     |
| update_at  | daytime | null: false                     |

### Association
- belongs_to :user
- belongs_to :group
- 

## membersテーブル

| Column   | Type    | Options                        |
| -------- | ------- | ------------------------------ |
| user_id  | integer | null: false, foreign_key: true |
| group_id | integer | null: false, foreign_key: true |

### Association
- belongs_to :group
- belongs_to :user
  