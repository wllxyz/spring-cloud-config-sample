# spring-cloud-config-sample
spring-cloud-config-sample

端口可以触发配置更新
http://localhost:8080/refresh

spring-boot项目端口映射情况查看
http//localhost:8080/mappings

环境配置
http//localhost:8080/env

项目要点：
1. 配置服务器
1a. 代码添加注解
@EnableConfigServer
1b. 配置文件中配置(bootstrap.properties)    
spring.cloud.config.server.git.uri=https://github.com/wllxyz/spring-cloud-config-sample.git
1c. pom.xml项目依赖添加    
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-config-server</artifactId>
        </dependency>


2.spring-cloud应用程序    
2a. 代码在需要更新配置的地方添加@RefreshScope注解    
2b. 配置文件中配置   
<pre>
#应用名
spring.application.name=a-bootiful-client
# N.B. this is the default:
#配置服务器地址
spring.cloud.config.uri=http://localhost:8888 
management.security.enabled=false
</pre>
2c.pom.xml项目依赖
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-config</artifactId>
		</dependency>
