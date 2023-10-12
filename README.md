# README


#　テーブル設計

## usersテーブル

| Colum                 | Type     | Options                   |
| --------------------- | -------- | ------------------------- |
| email                 | string   | null: false, unique: true |
| encrypted_password    | string   | null: false               |
| name                  | string   | null: false               |
| profile               | text     | null: false               |
| occupation            | text     | null: false               |
| position              | text     | null: false               |

### Association

- has_many :prototypes
- has_many :comments

## prototypeテーブル

| Colum                 | Type      | Options                        |
|---------------------- | --------- | ------------------------------ |
| title                 | string    | null: false                    |
| catch_copy            | text      | null: false                    |
| concept               | text      | null: false                    |
| user                  | reference | null :false, foreign_key: true |

### Association

- belongs_to :user
- has_many :comments

## commentsテーブル

| Colum                | Type       | Option                         |
| -------------------- | ---------- | ------------------------------ |
| content              | text       | null: false                    |
| prototype            | reference  | null: false, foreign_key: true |
| user                 | reference  | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype