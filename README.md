# Laravel で rest api を作る試み

## 前提

- 必要な php モジュールは導入済み
- node か bun が導入済み

## データベースの用意

```bash
# mariadb (sqlサーバー)にログイン
sudo mysql -u root
```

```sql
-- ユーザーの新規作成
create user 'new_user_name'@'localhost' identified by 'anypassword';

-- データベースの新規作成
create database new_db_name;

-- 上記で作ったデータベースに対する全権限を、上記のユーザーに与える。
grant all on new_db_name.* to new_user_name@localhost
```

この作業中によく使うSQL文。

```sql
-- データベースの一覧表示
show databases;

-- ユーザーの一覧表示
select user,host from mysql.user;

-- 権限確認
show grants for usre@localhost;
```

## laravel 11 のインストール

```bash
composer create-project laravel/laravel new_project_name

# インストール後
cd new_project_name

npm i
# または
bun i
```
