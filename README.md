# php8.0和php8.1 for phpStudy（小皮面板）（内含所需VC运行库）

phpstudy 8.1是个很好用的PHP集成环境软件，可惜官方一年多没更新了，官方只支持到PHP7.4，因为近期项目需要用到PHP8.1，所以自己动手配置了，考虑到很多网友可能也有这个需要，所以这里共享一下phpstudy8.1快速配置php8.0和php8.1的方法。已配置好的文件，直接复制粘贴后，就可以拿来用了。

【声明：这不算是开源项目，为的只是方便那些有需要的人，不喜欢可以绕道但请不要指责哦~】


### phpstudy8.1安装php8.0.14nts和php8.1.1nts的方法

按照“安装说明.txt”，复制粘贴即可正常使用。


### 安装说明


1、首先确保phpstudy 8.1（其他版本没测试，可自行测试）安装在默认目录，即：D:\phpstudy_pro\。
     如果不是默认目录，可以自行修改php.ini文件，将里面的：extension_dir = "D:\phpstudy_pro\Extensions\php\php8.0.14nts\ext" 修改为对应的目录即可。

2、直接复制php8.0.14nts和php8.1.1nts两个文件夹到：D:\phpstudy_pro\Extensions\php

3、安装VC运行库：双击目录里的“VC_redist.x64--Visual Studio 2015、2017、2019 和 2022 年.exe”文件安装。

4、重启phpstudy 8.1，即可选新安装的PHP版本了。

PS：如果重启phpstudy后PHP8仍不可用，请确认已经安装完成VC运行库。（测试方法：可以双击php.exe看看能否运行）



### 感谢支持：

支持本程序，请到Gitee和GitHub给我们点Star！

Gitee：https://gitee.com/caozha/caozha-admin

GitHub：https://github.com/cao-zha/caozha-admin

谢谢您的支持！

### 关于开发者

开发：邓草 www.caozha.com   微博：https://weibo.com/dengzhenhua

鸣谢：品络 www.pinluo.com