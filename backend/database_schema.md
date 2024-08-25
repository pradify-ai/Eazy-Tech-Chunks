# Database Schema

## User

- id: Integer (Primary Key)
- username: String (Unique)
- email: String (Unique)
- password_hash: String
- created_at: DateTime
- last_login: DateTime
- profile_picture_url: String
- bio: Text

## Article

- id: Integer (Primary Key)
- title: String
- content: Text
- summary: Text
- source_url: String
- published_at: DateTime
- created_at: DateTime
- category_id: Integer (Foreign Key to Category)
- author: String
- image_url: String
- likes_count: Integer
- views_count: Integer

## Category

- id: Integer (Primary Key)
- name: String
- description: String
- icon_url: String

## UserPreference

- id: Integer (Primary Key)
- user_id: Integer (Foreign Key to User)
- category_id: Integer (Foreign Key to Category)

## SavedArticle

- id: Integer (Primary Key)
- user_id: Integer (Foreign Key to User)
- article_id: Integer (Foreign Key to Article)
- saved_at: DateTime

Relationships:

- User can have many UserPreferences
- User can have many SavedArticles
- Category can have many Articles
- Category can have many UserPreferences
- Article can have many SavedArticles
