# intelliJ IDEA 运行第一个spring boot 程序出错

## 系统环境:Macos 10.11.6
## intelliJ IDEA（下称IDEA）

create new project -> Spring Initializr -> 按默认设置一路 next;

问题：

左侧Project一栏中打开pom.xml，提示 Failed xxx SpringFramework。

解决办法：

打开IDEA的perfence，搜索maven,User settings file 和 Local repository 勾选 Override。

命令行输入 mvn --verion 查看maven路径，显示为/usr/local/Cellar/maven/3.6.0/libexec。

找到该目录下的conf/settings.xml，复制一份到User settings file。

打开复制后的文件，搜索mirrors,在mirrors标签中添加一个可以访问的镜像。

一个可以访问的镜像：

```xml
<mirror>
    <id>uk.maven.org</id>
    <mirrorOf>central</mirrorOf>
    <name>UK Central</name>
    <url>http://uk.maven.org/maven2</url>
</mirror>
```

回到IDEA中相关的依赖就会自动下载。

另：

little snitch防火墙会显示 no code signature，没有细究，直接关了防火墙，等软件下载好了再打开即可。







