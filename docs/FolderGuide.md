

# 目录介绍

app/
默认情况下, 该文件夹主要包含 desing、i18n和etc三个子目录. app/code// 目录应该包含所有你创建的自定义模块. 也推荐在这里存储所有的第三方模块.

你的自定义门店主题(website主题)应该存储在app/design/frontend子目录, 同时app/design/adminhtml 子目录用来存储所有的Admin主题.

app/i18n 目录存储语言包. 你可能会用这个目录来创建一个满足客户需求的多语言门店.

code子目录在安装完成后会消失.

为了避免和自定义模块混在一起, 所有的Magento核心模块在vendor文件夹。通过Composer安装所有的包括Magento核心模块的依赖包。不建议在这个目录下工作, 因为一旦你更新安装, 你的变更将会被覆盖。

强烈推荐在 app/code/ 或者 app/design 目录下扩展模块。

phpserver/
这个目录包含Router.php文件, 这个文件的主要目的是实现PHP内建的服务器. 不建议使用此文件, 因为他有很多潜在的安全漏洞.

bin/
这个目录包含Magento CLI可执行脚本。这些脚本智行Magento脚本, 用来帮助你清理缓存、重新索引等

setup/
包含Magento的安装文件

generated/
存储所有Magento的生成的代码。默认的，如果将类注入到构造函数中，Magento会生成代码以创建不存在的工厂类。

var/
包含生成的类、缓存、会话、数据库备份以及缓存错误报告。这个目录有一些子目录，包括通过执行php bin/magento setup:di:compile, 内容会生成一次的var/di.

var/log 包括Magento的日志文件, 主要是exception.log 和 system.log文件
var/cache 存储所有Magento的缓存. 为了看到你的开发效果, 建议使用bin/magento cache:clean来持续清理缓存。
dev/
包含Magento测试框架运行的自动化功能测试

lib/
存储所有Magento和vendor库文件. 也包含所有Magento非模块代码。更多是帮助Magento运行的系统代码。

pub/
这个目录包含一个index.php文件，用来以生产模式运行系统。pub目录提供了一种安全机制，限制了对根目录资产的公共访问。这个目录也包括了Magento主题生成的静态文件。
