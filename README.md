# womanandchildhealth
Java：188 基于springboot妇幼健康管理系统
> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

本妇幼健康管理系统分为管理员、用户、医生三个权限。

管理员可以管理用户、医生的基本信息内容，可以管理药物信息以及患者预约信息等操作。

用户可以查看患者信息，可以查看药物以及个人就诊档案健康信息等操作。

另外医生可以查看患者的预约信息，进行诊疗安排，将记录和管理患者的医疗服务记录，医生可以查看患者的历史记录，以便更好地了解患者的病情和治疗情况，为诊断和治疗提供参考。

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

​

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：SpringBoot + MyBatis + Vue + Bootstrap + jQuery

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq


源码地址：[http://www.codegym.top](http://www.codegym.top/)



# 运行截图

## 文档截图

![img](https://i-blog.csdnimg.cn/img_convert/0d47c535268911769461a0a9770879ba.png)

![image20241219214547240](https://i-blog.csdnimg.cn/img_convert/8898c40523deb865158a1a23d10db320.png)

####

#### 项目截图

![图片1](https://i-blog.csdnimg.cn/img_convert/5a931719bad438a5f2f2d98d1caad9fe.png)

![图片2](https://i-blog.csdnimg.cn/img_convert/7ca6048bdd25c5d294b2f503fb29e6c9.png)

![图片3](https://i-blog.csdnimg.cn/img_convert/c7bb211d44cb1f172706f32ca2284bed.png)

![图片4](https://i-blog.csdnimg.cn/img_convert/d4050426c7267a751adad0d822846d99.png)

![图片5](https://i-blog.csdnimg.cn/img_convert/b585f96e3592ba9b49ecd0f991901950.png)

![图片6](https://i-blog.csdnimg.cn/img_convert/735e1ce66921ada58411afa02327e9de.png)
### 代码

```
    @Scheduled(cron = "0 0 1 * * ?")
    @SchedulerLock(name = "SystemResource.clearLogin", lockAtMostFor = "5s", lockAtLeastFor = "5s")
    public void clearLoginLog() {
        log.info("执行清除30天前的登录日志时间:{} " , LocalDateTime.now());
        long thirtyDaysMillisFromLocalDate = getThirtyDaysMillisFromLocalDate(60L);
        userLoginLogService.clearData(thirtyDaysMillisFromLocalDate);
    }
```
