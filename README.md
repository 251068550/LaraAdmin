## 关于 ##
这是基于laravel5.4开发的后台权限管理系统，可做为项目开发的基本模版。后续会添加前台的例子。

## 功能 ##
- 控制台
- 系统管理
 - 用户管理
 - 角色管理
 - 权限管理
 - 菜单管理
 - 系统日志


## 安装 ##
下载项目到本地
```
git clone https://github.com/251068550/LaraAdmin.git
```
compoer安装
```
cd LaraAdmin
composer install
```
> 如果composer install安装很慢，推荐安装国内镜像
> 执行 `composer config -g repo.packagist composer https://packagist.phpcomposer.com`

配置.env文件
```
cp .env.example .env
```
配置数据库
```
DB_HOST=localhost
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```
生成APP_KEY
```
php artisan key:generate
```
数据库迁移(记得先创建配置的数据库)
```
php artisan migrate --seed
```
这样项目就部署好了，后台的登录路由是
http://localhost:(端口)/LaraAdmin/public/login
管理员帐号：admin，密码：123456

**Enjoy yourself!**

## 进行开发 ##
本项目使用了prettus/l5-repository扩展包，可以通过命令生成model，controller等，开发前可运行命令新建模型控制器等。更多命令查看官方文档[prettus/l5-repository](https://packagist.org/packages/prettus/l5-repository)
```
php artisan make:entity
```
> 注意：执行上面代码应该会报错失败。因为I5-repository支持到laravel5.3，5.4有个laravel的底层库文件修改了名称，导致引用不到。需要到目录 \vender\prettus\I5-repository\src\Prettus\Repository\Generators\Generator.php 修改引用的文件 AppNamespaceDetectorTrait 为 DetectsApplicationNamespace 
> 这个错误必然出现，除非作者更新仓库。所以会尽快提示作者修复这个问题。