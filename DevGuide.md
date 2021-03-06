
## 创建模块文件和目录

在Magento2中, 模块通过命名空间进行分组，直接放在 app/code 目录.
我们第一步是创建模块目录和注册模块所需要的必要文件。
1. 创建app/code/{namespace}/{modulename}目录
1. 创建app/code/{namespace}/{modulename}/etc/module.xml文件
1. 创建app/code/{namespace}/{modulename}/registration.php文件
1. 执行bin/magento setup:upgrade命令, 

模型：系统模型层。 它的主要范围是处理系统业务规则和持久化数据。
视图：这负责用户信息显示层，例如产品页面和联系表单。 由布局文件控制，该布局文件将块、容器和UI组件组装到页面中，以供Web浏览器显示。 块由PHP代码支持以生成动态页面内容。 它们通常与易于自定义的PHTML模板文件配对，以生成组合到页面中的HTML片段。
控制器：该层定义了可能改变模型状态并生成模型层数据视图的客户端的主要动作，请求和响应。控制器控制页面流和表单提交的编排。 Magento遵循标准的MVC模式，提供了良好的关注点分离，以实现增强的模块化。

# Magento多语言网站设置

在全球发展业务，请不要忘记将前端内容翻译成目标国家/地区的语言。 要创建多语言商店，您需要配置网站本地化版本。

设置非常简单。 首先，选择三种方式中的哪一种：

1. 创建一个新网站：该方式允许创建一个具有唯一名称的单独网站。 此外，您将设法创建和分配多个商店，并为其存储视图；
2. 创建一个新商店：如果您不仅要制作本地化版本，而且要制作具有足够差异的商店，那么选择是合理的。 为此，您需要创建一个网站，添加商店和商店视图；
3. 创建一个新的商店视图：方法是最简单的，因为您可以简单地向当前商店添加本地化版本。
   然后继续进行后端设置。

### Create a new website

 