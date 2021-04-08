# dubbo_provider_and_consumer
Dubbo分布式服务框架入门

微服务架构的那些事儿
https://blog.csdn.net/weixin_43529556/article/details/115434260?utm_medium=distribute.pc_feed_category.none-task-blog-u_c_null-3.nonecase&dist_request_id=1328767.82179.16177764873783289&depth_1-utm_source=distribute.pc_feed_category.none-task-blog-u_c_null-3.nonecase

Dubbo分布式服务框架入门（附工程）
https://blog.csdn.net/u013142781/article/details/50387583

####################################################
代码运行：
源码：dubbo_provider_and_consumer，dubbo消费和提供者实例
https://download.csdn.net/detail/u013142781/9377617

####################################################
启动：dubbo-admin
http://localhost:8090/dubbo-admin
用户: root 
密码：root

启动服务者：provider
保持这个provider一直启动着。 同时在duubo-admin上搜索：com.luo.service.TestService，会看到如下结果：

启动消费者：consumer
前提：依赖服务者，那么 provider 项目必须使用 maven 的install命令打包到本地的maven库中
<dependency>  
  <groupId>com.luo</groupId>  
  <artifactId>provider</artifactId>  
  <version>0.0.1-SNAPSHOT</version>  
</dependency>  

打包之后，需要在 consumer中进行pom.xml的import更新操作
运行 在保持zookeeper、dubbo-admin和provider运行着的基础上，运行ConsumerServiceTest.java，Run As –> Java Application，会看到控制台如下：
luoguohui
没错，就是provider的提供

控制台内容luoguohui就是提供者打印出来的 另外也会看到dubbo-admin中com.luo.service.TestService有消费者了：

####################################################
下一个目标：
1.服务者和消费者改为 springboot形式
2.zk进行本地启动模式




####################################################
dubbo-admin管理平台搭建
https://blog.csdn.net/u013142781/article/details/50396621

配置tomcat：跟文章一样，改为：8090
http://localhost:8090/dubbo-admin

目的：打包：dubbo-admin的war包放到端口修改为8090的
tomcat中配置：
root 的密码：root
guest 的密码：guest

配置zookeeper：本次的局域网中有环境：172.16.95.230
dubbo.registry.address=zookeeper://172.16.95.230:2181

#######################
代码版本：文章中是2.5.4，本次是 2.5.x 具体打包后为： dubbo-admin-2.5.10.war
github的中国代理：codechina 使用分支： 2.5.x 
https://codechina.csdn.net/mirrors/alibaba/dubbo/-/tree/2.5.x
原地址：
https://github.com/alibaba/dubbo

#######################
文章中：
dubbo-admin-2.5.4-SNAPSHOT.war
Tomcat 7.0\webapps\dubbo-admin-2.5.4-SNAPSHOT\WEB-INF
dubbo.properties
做配置：
dubbo.registry.address=zookeeper://127.0.0.1:2181
dubbo.admin.root.password=root
dubbo.admin.guest.password=guest

访问：
http://localhost:8090/dubbo-admin-2.5.4-SNAPSHOT/
#######################
本机中修改：
直接在代码中打包：
修改文件：D:\work\RPC\dubbo-2.5.x\dubbo-admin\src\main\webapp\WEB-INF
dubbo.properties
修改：
dubbo.registry.address=zookeeper://172.16.95.230:2181
dubbo.admin.root.password=root
dubbo.admin.guest.password=guest
配置tomcat：跟文章一样，改为：8090
http://localhost:8090/dubbo-admin



#######################




####################################################
