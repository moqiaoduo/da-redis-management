# DirectAdmin Redis Management Plugin
原版未适配Evolution皮肤，因此修改下。顺便把模板也汉化了，不考虑英文的使用。

因为改动的地方可能跟原版不兼容，故不作Pull Request，以免更改原版的“原汁原味”。

The Original Plugin doesn't fit the skin Evolution, so I fix it.

I won't do "Pull Request" because of incompatible modification.

Original Description:
```
Welcome to this repository of an unofficial DirectAdmin plugin for managing Redis instances. 

With this plugin end-users on an DirectAdmin server can easliy add and remove their redis instances.

I developed and used this plugin for over a year now on our own servers, but I decided to release it to the public! So everyone can use this.
```

# Installation
## Requirements
This plugin works on every DirectAdmin server, but the included setup script is only for RHEL/CentOS with systemctl support. Maybe I will add install scripts for Ubuntu / Debian in the future. （大概含义就是一键安装redis需要systemctl支持，目前还没有对U/D两个系统进行支持，但是插件的安装只要是directadmin都支持）

For enabeling, starting and stopping for redis instances it uses sudo with minimal permissions.

## Redis installation（Redis一键安装，PHP扩展用的pecl安装，所以只能装到默认PHP版本，其他需要手动装）
```
cd /usr/local/directadmin/plugins/redis_management/setup
sh install.sh
```
注意先进行这步再进行插件安装，否则redis权限设置时会出错

## Plugin installation（插件安装）
```
cd /usr/local/directadmin/plugins
git clone https://github.com/kbentlage/da-redis-management.git redis_management
sh redis_management/scripts/install.sh
```

# Configuration
By default, the plugin is working out-of-the box. But it can be needed to change serveral configuration settings.

The default settings are stored in /usr/local/directadmin/plugins/redis_management/php/Config/main.php.

If you need to change for example the location where the redis data is stored (default in /var/lib/redis), you can do this in "local.php". Please do not change this in the "main.php" config file, because this file can be overwritten when a new version of this plugin is installed.

# Update
```
cd /usr/local/directadmin/plugins/redis_management
git pull
```

# Screenshots
List Redis instances

![List Redis instances](https://raw.githubusercontent.com/moqiaoduo/da-redis-management/master/screenshots/list.png)