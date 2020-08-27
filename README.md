# テーブル設計

## users テーブル

| Column    | Type      | Options     |
| --------- | --------- | ----------- |
| name      | string    | null: false |
| email     | string    | null: false |
| password  | string    | null: false |

### Association

- has_many :room_users
- has_many :rooms, through: :room_users
- has_many :messages

## rooms テーブル

| Column  | Type      | Options     |
| ------- | --------- | ----------- |
| name    | string    | null: false |

### Association

- has_many :rooms_users
- has_many :users, through: :rooms_users
- has-many :messages

## room_users テーブル

| Column  | Type        | Options                       |
| ------- | ----------- | ----------------------------- |
| user    | refernces   | null: false foreign_key: true |
| room    | refernces   | null: false foreign_key: true |

### Association

- belongs_to :user
- belongs_to :room

## messages テーブル

| Column  | Type        | Options                       |
| ------- | ----------- | ----------------------------- |
| content | string      |                               |
| user    | refernces   | null: false foreign_key: true |
| room    | refernces   | null: false foreign_key: true |

### Association

- belongs_to :user
- belongs_to :room