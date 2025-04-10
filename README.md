## 成果物雛形
- 図
    + システム全体図
    + 業務フロー図
    + 画面遷移図
    + ＥＲ図
    + CRUD図
    + ジョブフロー図

- 一覧
    + サブシステム一覧
    + インターフェース一覧
    + 機能一覧
    + 画面一覧
    + 帳票一覧
    + PGM一覧
    + JOB一覧
    + テーブル一覧
    + ファイル一覧


### :computer: Progaming Language 基本構文比較表
<hr>

- [C](https://github.com/sixsGod/study/tree/master/C)
- [Java](https://github.com/sixsGod/study/tree/master/java)
- [Python](https://github.com/sixsGod/study/tree/master/pytohn)
- [Cobol](https://github.com/sixsGod/study/tree/master/COBOL)
- [Shell](https://github.com/sixsGod/study/tree/master/Linux)
- [BAT](https://github.com/sixsGod/study/tree/master/BAT)
- [VBA](https://github.com/sixsGod/study/tree/master/VB)
- [Swift](https://github.com/sixsGod/study/tree/master/swift)

|编程语言|C|Java|Python|Cobol|Shell|BAT|VBA|Swift|
|-|-|-|-|-|-|-|-|-|
|コメント|// コメント|// コメント|# コメント|* コメント|# コメント|REM コメント|'コメント|-|
|変数宣言|-|-|-|-|-|-|-|-|
|データ型|-|-|-|-|-|-|-|-|
|式と演算子|-|-|-|-|-|-|-|-|
|条件分岐|-|-|-|-|-|-|-|-|
|ループ|-|-|-|-|-|-|-|-|
|関数定義|-|-|-|-|-|-|-|-|
|メッセージ入力|-|-|-|-|-|-|-|-|
|メッセージ出力|-|-|-|-|-|-|-|-|
|配列|-|-|-|-|-|-|-|-|
|エラー処理|-|-|-|-|-|-|-|-|
|モジュール|-|-|-|-|-|-|-|-|

### :floppy_disk: Database 基本構文比較表
<hr>

- [Oracle](https://github.com/sixsGod/study/tree/master/sql/oracle)
- [Mysql](https://github.com/sixsGod/study/tree/master/sql/mysql)
- [PostgreSQL](https://github.com/sixsGod/study/tree/master/sql/postgres)
- [DB2](https://github.com/sixsGod/study/tree/master/sql/db2)
- [SQL Server](https://github.com/sixsGod/study/tree/master/sql/SQL%20Server)

|功能语法|Oracle|Mysql|PostgreSQL|DB2|SQL Server|
|-|-|-|-|-|-|
|数据库安装|推荐docker安装|sudo apt install mysql-server|sudo apt install postgresql |推荐docker安装|sudo apt install -y mssql-server|
|服务启动|默认端口1521|3306|5432|50000|1433|
| ---- 启动|sudo systemctl start oracle-xe-19c|sudo systemctl start mysql|sudo systemctl start postgresql|docker start db2|sudo systemctl start mssql-server|
| ---- 停止|sudo systemctl stop oracle-xe-19c|sudo systemctl stop mysql|sudo systemctl stop postgresql|docker stop db2|sudo systemctl stop mssql-server|
| ---- 状态|sudo systemctl status oracle-xe-19c|sudo systemctl status mysql|sudo systemctl status postgresql|docker exec -it db2 bash|sudo systemctl status mssql-server|
|数据库连接|sqlplus/Oracle SQL Developer|mysql命令/MySQL Workbench|psql/pgAdmin|DB2命令/IBM Data Studio|sqlcmd/SQL Server Management Studio（SSMS）|
|数据类型|-|-|-|-|-|
| *数据库操作* |-|-|-|-|-|
| ---- 创建|⛔(CREATE USER + GRANT)|CREATE DATABASE dbname;|CREATE DATABASE dbname;|CREATE DATABASE dbname;|CREATE DATABASE dbname;|
| ---- 使用|⛔|use dbname;|\c dbname|CONNECT TO dbname;|use dbname;|
| ---- 删除|⛔(DROP USER + SCHEMA)|DROP DATABASE dbname;|DROP DATABASE dbname;|DROP DATABASE dbname;|DROP DATABASE dbname;|
| *数据表操作* |-|-|-|-|-|
| ---- 创建|CREATE TABLE|CREATE TABLE|CREATE TABLE|CREATE TABLE|CREATE TABLE|
| ---- 修改|ALTER TABLE|ALTER TABLE|ALTER TABLE|ALTER TABLE|ALTER TABLE|
| ---- 删除|DROP TABLE|DROP TABLE|DROP TABLE|DROP TABLE|DROP TABLE|
| ---- 项目表示|desc tbname|DROP TABLE|DROP TABLE|DROP TABLE|DROP TABLE|
| *数据操作* |-|-|-|-|-|
| ---- 创建|-|-|-|-|-|
| ---- 检索|-|-|-|-|-|
| ---- 删除|-|-|-|-|-|


