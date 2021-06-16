   users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

    Association

- has many :prototype_users
- has many :prototypes, through: :prototype_users
- has many :comments

   prototypes テーブル

| Column     | Type       | Options      |
| ---------- | ---------- | ------------ |
| title      | string     |  null: false |
| catch_copy | text       |  null: false |
| concept    | text       |  null: false |
| image      |            |              |
| user       | references |              |

    Association

- has_many :prototype_users
- has many :users,through: :prototype_users
- has_many :comments

  prototype_users テーブル

| Column    | Type       | Options                        |
| ----------| ---------- | ------------------------------ |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

    Association

- belongs_to :user
- belongs_to :prototype

   comments テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

    Association

- belongs_to :user
- belongs_to :prototype