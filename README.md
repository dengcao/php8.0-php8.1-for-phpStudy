# php7.4至php8.5 for phpStudy（小皮面板）（内含所需VC运行库）

phpstudy 8.1是个很好用的PHP集成环境软件，可惜官方很久没更新了，官方只支持到PHP8.0和PHP8.2，因为近期项目需要用到PHP8.5，所以自己动手配置了，考虑到很多网友可能也有这个需要，所以这里共享一下phpstudy8.1快速配置php7.4至php8.5的方法。已配置好的文件，直接复制粘贴后，就可以拿来用了。

【声明：这不算是开源项目，为的只是方便那些有需要的人，不喜欢可以绕道但请不要指责哦~】

### 推荐使用：phpstudy8.1离线版安装包

如需要在局域网内安装离线版，请移步：

Gitee：https://gitee.com/dengzhenhua/phpstudy

GitHub：https://github.com/dengcao/phpStudy


### phpstudy8.1安装php7.4.33nts至php8.5.3nts的方法

按照“安装说明.txt”，复制粘贴即可正常使用。


### 安装说明


1、首先确保phpstudy 8.1（其他版本没测试，可自行测试）安装在默认目录，即：D:\phpstudy_pro\。
     如果不是默认目录，可以自行修改php.ini文件，以php8.0.30nts为例，将里面的：extension_dir = "D:\phpstudy_pro\Extensions\php\php8.0.30nts\ext" 修改为对应的目录即可。

2、直接复制php7.4.33nts至php8.5.3nts等多个PHP文件夹到：D:\phpstudy_pro\Extensions\php

3、安装VC运行库：双击目录里的“VC_redist.x64--Visual Studio 2015、2017、2019 和 2022 年.exe”文件安装。

4、重启phpstudy 8.1，即可选新安装的PHP版本了。

PS：如果重启phpstudy后PHP8仍不可用，请确认已经安装完成VC运行库。（测试方法：可以双击php.exe看看能否运行）

如需要更多PHP版本，请到官网下载：https://downloads.php.net/~windows/releases/archives/


### 【2026-10-22 更新说明】
近日，PHP曝出两个严重安全漏洞（代号“php2shell”），漏洞编号为CVE-2026-109618、CVE-2026-109619。该漏洞可导致未经身份验证的远程攻击者通过发送特制POST请求，触发内存破坏并最终实现远程代码执行，从而获取服务器控制权限。漏洞影响PHP 8.5.x＜8.5.12、PHP 8.4.x＜8.4.27、PHP 8.3.x＜8.3.36、PHP 8.2.x＜8.2.35以及8.1以前版本。由于漏洞危害严重，已导致多国网站大规模紧急下线。PHP作为一种开源编程语言，广泛应用于WordPress、Drupal、Joomla和Magento等网站平台开发。目前，PHP官方已发布最新版本（8.5.12、8.4.27、8.3.36、8.2.35）修复该漏洞，详见：https://www.php.net/archive/2026.php#2026-10-21-5 建议受影响用户及时更新至安全版本，消除安全隐患，严防发生网络攻击事件。

**目前，本离线安装包已经集成了PHP官方最新版本，请建站时尽量使用这些PHP版本：8.5.12、8.4.27、8.3.36、8.2.35。**


此外，已经针对PHP旧版本增加了临时缓解设置，以尽量减少被攻击的可能。主要更改php.ini代码设置如下：

> ; ============================================
>
> ; PHP2Shell (CVE-2026-109618 / CVE-2026-109619) 临时缓解配置
>
> ; 仅用于无法立即升级时的风险降低，并非完整修复
>
> ; ============================================
>
> ; --- 针对 CVE-2026-109619 (会话状态污染) 的缓解 ---
>
> ; 禁用会话上传进度功能即可；不要再设 cleanup=Off
>
> session.upload_progress.enabled = Off
>
> ; 通用会话加固（PHP < 5.5.2 不识别 strict_mode，属正常）
>
> session.use_strict_mode = 1
>
> session.use_only_cookies = 1
>
> session.cookie_httponly = 1
>
>
> ; --- 针对 CVE-2026-109618 (内存耗尽/OOM损坏) 的缓解 ---
>
> ; 关键：memory_limit=-1 建议在 PHP-FPM 池里用 php_admin_value 设置，
>
> ; 而不是只写在 php.ini，否则可能被应用 ini_set('memory_limit', ...) 覆盖
>
> memory_limit = -1
>
> ; 限制请求体大小；确保 upload_max_filesize < post_max_size
>
> ; 不需要上传可改为 8M
>
> post_max_size = 32M
>
> ; 输入嵌套层级；常规业务 6 一般够，复杂嵌套 API 可调到 10/16
>
> max_input_nesting_level = 6
>
> ; （仅 PHP 8.5 适用，更低版本忽略此项）关闭致命错误回溯，减少信息泄露
>
> ; fatal_error_backtraces = 0
>




### 感谢支持：

请到Gitee和GitHub给我点Star，谢谢您的支持！

Gitee：https://gitee.com/dengzhenhua/php8.0-8.1-for-phpstudy

GitHub：https://github.com/dengcao/php8.0-php8.1-for-phpStudy


### 关于

开发：[邓草博客 blog.5300.cn](http://blog.5300.cn)

赞助：[品络互联 www.pinluo.com](http://www.pinluo.com)  &ensp;  [AI工具箱 5300.cn](http://5300.cn)  &ensp;  [汉语言文学网 hyywx.com](http://hyywx.com)  &ensp;  [源码社区 bbs.ym.gs](http://bbs.ym.gs)  &ensp;  [雄马 xiongma.cn](http://xiongma.cn) &ensp;  [优惠券 tm.gs](http://tm.gs)  &ensp;  [AI创作助手 aiczzs.com](http://aiczzs.com)  &ensp;  [AI一键生成 aiyjsc.com](http://aiyjsc.com)  &ensp;  [API中转站 apizz.vip](http://apizz.vip)
