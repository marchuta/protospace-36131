# README

## users テーブル
| Column             | Type  | Options     |
| ----------------   | ------| ----------- |
| name               | string| null: false |
| email              | string| null: false |
| encrypted_password | string| null: false |
| profile            | text  | null: false |
| occupation         | text  | null: false |
| position           |text   | null: false |

### Association 
- has_many :prototypes
- has_many :comments


## prototypes テーブル
| Column             | Type  | Options     |
| ----------------   | ------| ----------- |
| title              | string| null: false |
| catch_copy         | text  | null: false |
| concept            | text  | null: false |
| image              | active storage  | null: false |
| user               | references| null: false |

### Association 
- has_many :comments
- belongs_to :user


## comments テーブル
| text               | text  | null: false |
| user               | references  | null: false |
| prototype          |references| null: false |

### Association 
- belongs_to :prototype
- belongs_to :user