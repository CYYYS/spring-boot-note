    
    因为“习惯优先于配置”的原则，使得Spring Boot在快速开发应用和微服务架构实践中得到广泛应用。经过阅读官方文档和查阅资料，以helloworld为例子学习pom的几个主要配置。

    1.配置pom主要的依赖

	<!-- Spring Boot 启动父依赖 -->
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.3.3.RELEASE</version>
    </parent>
 
    <dependencies>
        <!-- Spring Boot web依赖 -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
 
        <!-- Junit -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.12</version>
        </dependency>
    </dependencies>
	
    2.controller层
		
	@RestController
	public class HelloWorldController {
 
  	  @RequestMapping("/")
    	public String sayHello() {
    	    return "Hello,World!";
   	 }
	}

	@RestController和@RequestMapping注解是来自SpringMVC的注解，它们不是SpringBoot的特定部分。

	1. @RestController：提供实现了REST API，可以服务JSON,XML或者其他。这里是以String的形式渲染出结果。

	2. @RequestMapping：提供路由信息，"/“路径的HTTP Request都会被映射到sayHello方法进行处理。

    3.@SpringBootApplication
	public class Application {
 
   	 	public static void main(String[] args) {
        		SpringApplication.run(Application.class,args);
    		}
	}
	1）. @SpringBootApplication：Spring Boot 应用的标识

	2）. Application很简单，一个main函数作为主入口。SpringApplication引导应用，并将Application本身作为参数传递给run方法。具体run方法会启动嵌入式的Tomcat并初始化Spring环境及其各Spring组件。

	以上介绍了helloword的最简单的一个springboot的项目。