# Vercel部署Typecho博客系统

## 第一步
1.Github创建一个仓库 设置为private  
2.克隆本仓库代码到你创建的仓库

## 第二步
1.获取一个数据库可自己搭建也可以自己找
我这边推荐[railway](https://railway.app/)  
2.注册一个账号并新建MySQL数据库  
3.修改config.inc.php中
```
/** 定义数据库参数 */
$db = new Typecho_Db('Pdo_Mysql', 'typecho_');
$db->addServer(array (
  'host' => '请填入数据库地址',
  'user' => '数据库用户名',
  'password' => '数据库密码',
  'charset' => 'utf8',
  'port' => '3306',
  'database' => '数据库名称',
  'engine' => 'MyISAM',
), Typecho_Db::READ | Typecho_Db::WRITE);
Typecho_Db::set($db);

```
修改成自己的数据库

## 第三步
使用Vercel部署github仓库


## pbloods大佬做的一键部署
https://vercel.com/import/project?template=https://github.com/pbloods/typecho/
