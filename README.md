# Vercel部署Typecho博客系统

## 一键部署
注册并登录好Vercel账号点击此链接可以直接跳转Vercel新建项目，效果与第一步类似（完成后可跳过第一步）  
[一键部署Vercel项目](https://vercel.com/button)(https://vercel.com/import/project?template=https://github.com/QzKevin/typecho_vercel)

## 第一步（使用一键部署跳过此步骤）
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
1.使用Vercel部署github仓库（使用一键部署跳过此步骤）  
2.用Vercel提供的域名 + /install.php开始安装（具体安装可自行搜索Typecho安装教程）

