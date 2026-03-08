## SVN概念
Apache Subversion 通常被缩写成 SVN，是一个开放源代码的版本控制分支管理系统
- repository（源代码库）:源代码统一存放的地方
- Checkout（提取）:当你手上没有源代码的时候，你需要从 repository checkout 一份
- Commit（提交）:当你已经修改了代码，你就需要Commit到repository
- Update (更新):当你已经 checkout 了一份源代码， update 一下你就可以和Repository上的源代码同步，你手上的代码就会有最新的变更

## SVN 操作
- SVN手动新建版本库
```
mkdir /opt/svn
svnadmin create /opt/svn/runoob01
# svnserve启动服务:SVN默认监听3690
svnserve -d -r 目录 --listen-port 端口号  -> svnserve -d -r /opt/svn/runoob01
[runoob@centos6 ~]# ll /opt/svn/runoob01/
total 24
drwxr-xr-x 2 root root 4096 2016/08/23 16:31:06 conf -> svnserve.conf 服务配置文件,authz权限配置文件
drwxr-sr-x 6 root root 4096 2016/08/23 16:31:06 db
-r--r--r-- 1 root root    2 2016/08/23 16:31:06 format
drwxr-xr-x 2 root root 4096 2016/08/23 16:31:06 hooks
drwxr-xr-x 2 root root 4096 2016/08/23 16:31:06 locks
-rw-r--r-- 1 root root  229 2016/08/23 16:31:06 README.txt
```
- SVN 检出操作
```
svn checkout http://svn.server.com/svn/project_repo --username=user01
svn add readme -- 将文件readme加到版本控制，等待提交到版本库
svn commit -m "SVN readme."  -- 存储到版本库中
svn revert readme  -- 放弃对文件的修改，版本回退，恢复目录用 -R 命令
svn merge -r 22:21 readme -- 恢复一个已经提交的版本
```
## SVN 解决冲突
```
svn status -- 查看工作副本中的状态
svn diff -- 查看更改
svn commit -m "up"  -- 尝试提交
svn update  -- 更新工作副本 mc；以本地的文件为主
svn update -r6 -- 指定更新到6版本
-- 此时工作副本是和仓库已经同步，可以安全地提交更改了
```
## SVN 查看历史信息
- svn log: 用来展示svn 的版本作者、日期、路径等等。 -> svn log -r 6:8(6-8之间的信息)/snv log filename
  + 如果希望显示限定N条记录的目录信息，使用 svn log -l [N] -v
- svn diff: 用来显示特定修改的行级详细信息。
  + 比较 svn 工作版本中版本号2和3的这个文件的变化 ,svn diff -r 2:3 rule.txt
- svn cat: 取得在特定版本的某文件显示在当前屏幕。
  + 检查一个过去版本，不希望查看他们的区别,svn cat -r 版本号 rule.txt
- svn list: 显示一个目录或某一版本存在的文件。
  + 不下载文件到本地目录的情况下来察看目录中的文件,svn list http://192.168.0.1/runoob01

## SVN分支
- trunk:开发主线
- branches:存放所有分支
- tags:存放所有标签
