## Postgres概要

## 数据类型
- smallint：2字节
- integer：4字节
- bigint：8字节
- decimal：可变长
- numeric：可变长
- real：4字节,可变精度，不精确
- Boolean：
- TEXT：变长，无长度限制
- JSON(JSONB)：二进制保存设定信息，metadata
- UUID：通用唯一标识符 userId，sessionId
- Serial：自动採番整数型

## PSQL
`版本确认`
```sql
sudo apt install postgres -- linux ubantu install command
psql --version
sudo -i -u postgres -- 切换postgres用户，空密码
psql -- 进入PSQL
```

`连接数据库`
```sql
/* 参数说明
  -h localhost
  -d database
  -U user
*/
psql -h localhost -d postgres -U postgres  -- 输入密码，进入PSQL

元命令：\l -- 显示数据库
CREATE DATABASE testdb; -- 创建testdb数据库
postgre=# \c testdb -- 连接testdb数据库
```

`重启服务`
```sql
sudo /etc/init.d/postgresql start   -- 开启
sudo /etc/init.d/postgresql stop    -- 关闭
sudo /etc/init.d/postgresql restart -- 重启
```


`创建数据表`
```sql
CREATE TABLE users (
  id UUID PRIMARY KEY,
  name TEXT,
  birthday DATE
);
```

`插入数据`
```sql
INSERT INTO users(id, name, birthday)
VALUES ('01956bbf-8799-7068-9b44-d32253725c7d','Allen','2000-01-02');
```
