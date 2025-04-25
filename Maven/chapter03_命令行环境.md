# 第三章 使用Maven: 命令行环境

## 014 Maven 命令行 实验一 核心概念: 坐标

![坐标](./images/014_a_maven_coordinate.png)
![坐标向量的取值方式](./images/014_b_maven_coordinate_values.png)

## 015 Maven 命令行 实验一 坐标和仓库目录的对应关系

![坐标和仓库目录的对应关系](./images/015_a_coordinate_path_mapping.png)

## 016 Maven 命令行 实验一 archetype命令说明

![创建工作空间](./images/016_a_working_space.png)
![archetype命令解析](./images/016_b_archetype_command.png)
![命令实例](./images/016_c_command_example.png)

## 017 Maven 命令行 实验一 执行命令创建工程

![实际生成java项目](./images/017_a_archetype_generate_executed.png)

## 018 Maven 命令行 实验一 对创建好的工程做一点调整

* 将工程里的`pom.xml`文件改为如下内容:  
![修改后的pom.xml](./images/018_a_pom_modified.png)

* 将生成的`App.java`和`AppTest.java`文件删除。

## 019 Maven 命令行 实验一 pom.xml解读

```
<?xml version="1.0" encoding="UTF-8"?>
<!-- 根标签: project，表示对当前工程进行配置、管理。 -->
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <!-- modelVersion标签: 从Maven2开始就固定是4.0.0。 -->
  <!-- 代表当前pom.xml所采用的标签结构。 -->
  <modelVersion>4.0.0</modelVersion>

  <!-- 坐标信息 -->
  <!-- 在本地仓库中安装后对应的路径: -->
  <!-- com\atguigu\maven\pro01-maven-java\1.0-SNAPSHOT\pro01-maven-java-1.0-SNAPSHOT.jar -->
  <!-- groupId标签: 坐标向量之一: 代表公司或组织开发的某一个项目 -->
  <groupId>com.atguigu.maven</groupId>
  <!-- artifactId标签: 坐标向量之一: 代表项目下的某一个模块 -->
  <artifactId>pro01-maven-java</artifactId>
  <!-- version标签: 坐标向量之一: 代表当前模块的版本 -->
  <version>1.0-SNAPSHOT</version>
  
  <!-- packaging标签: 打包方式 -->
  <!-- 取值jar: 生成jar包，说明这是一个Java工程。 -->
  <!-- 取值war: 生成war包，说明这是一个Web工程。 -->
  <!-- 取值pom: 说明这个工程是用来管理其它工程的工程。 -->
  <packaging>jar</packaging>

  <name>pro01-maven-java</name>
  <url>http://maven.apache.org</url>

  <!-- properties标签: 在Maven中定义属性值 -->
  <properties>
	<!-- 在构建过程中读取源码时使用的字符集 -->
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
  </properties>
  
  <!-- dependencies标签: 配置具体依赖信息，可以包含多个dependency子标签 -->
  <dependencies>
	<!-- dependency标签: 配置一个具体的依赖信息 -->
    <dependency>
	  <!-- 坐标信息: 导入哪个jar包，就配置它的坐标信息即可 -->
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.12</version>
	  
	  <!-- scope标签: 配置当前依赖的范围 -->
      <scope>test</scope>
    </dependency>
  </dependencies>
</project>
```

## 020 Maven 命令行 实验一 核心概念: POM

![POM概念](./images/020_a_pom_concept.png)

## 021 Maven 命令行 实验一 核心概念: 约定的目录结构

![目录结构](./images/021_a_directory_structure.png)
![约定](./images/021_b_convention_over_configuration.png)

## 022 Maven 命令行 实验二 添加Java代码

![添加Java代码](./images/022_a_add_java_code.png)

## 023 Maven 命令行 实验三 clean和compile命令

![Maven命令](./images/023_a_maven_command.png)
![编译命令](./images/023_b_command_compile.png)

* 执行`mvn compile`和`mvn test-compilel`后:  
![执行编译后](./images/023_c_after_compile.png)

* 执行`mvn clean`后:  
![执行clean后](./images/023_d_after_clean.png)

## 024 Maven 命令行 实验三 test命令

![test命令](./images/024_a_command_test.png)

![test命令画面](./images/024_b_test_result.png)

## 025 Maven 命令行 实验三 package命令

![package命令](./images/025_a_command_package.png)

* 执行`package`命令后:  
![执行package命令](./images/025_b_after_package.png)

## 026 Maven 命令行 实验三 install命令

![install命令](./images/026_a_command_install.png)  

* 执行`install`命令后:  

![执行install命令](./images/026_b_after_install.png)

## 027 Maven 命令行 实验四 生成Web工程 执行生成

![web工程](./images/027_a_webapp_archetype.png)  

```
mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-webapp -DarchetypeVersion=1.4
```

![生成web工程](./images/027_b_generate_web_project.png)  

## 028 Maven 命令行 实验四 生成Web工程 执行构建

* 添加如下Servlet, web.xml, jsp内容

![添加Servlet](./images/028_a_add_servlet.png)  
![添加web.xml](./images/028_b_add_web_xml.png)  
![添加jsp](./images/028_c_add_jsp.png)  

* 此时如果用maven执行编译不会通过，因为还没有引入servlet-api的jar包。在pom.xml中添加如下配置:

![添加servlet-api依赖](./images/028_d_servlet_api_dependency.png)  

* 使用`mvn package`命令进行打包，可看到生成的war包。

![生成war包](./images/028_e_package_war.png)  

## 029 Maven 命令行 实验四 生成Web工程 执行部署

* 将生成的war包或同名的目录复制到tomcat的webapps目录下，完成部署。

![tomcat部署](./images/029_a_deploy_to_tomcat.png)  

## 030 Maven 命令行 实验五 针对Web工程执行构建命令

![添加依赖](./images/030_a_add_dependency_in_web_project.png)  

![添加单元测试](./images/030_b_add_unit_test.png)  

1. 执行测试`mvn test`，可以看到测试成功通过。
1. 执行打包`mvn package`后，可以看到生成的war包的解压目录中的lib目录包含java工程的java包。
![打包后确认lib](./images/030_c_after_package_lib_included.png)
1. 查看当前工程的依赖的命令
  * `mvn dependency:list`
![依赖列表](./images/030_d_dependency_list.png)  

  * `mvn dependency:tree`
![树形依赖列表](./images/030_e_dependency_tree.png)  

## 031 Maven 命令行 实验六 依赖范围 测试compile范围 空间角度

![依赖的范围](./images/031_a_scope.png)  

* 验证`compile`范围的类在`main`中可用
![依赖的范围](./images/031_b_compile_in_main.png)  

* 验证`compile`范围的类在`test`中可用
![依赖的范围](./images/031_c_compile_in_test.png)  

## 032 Maven 命令行 实验六 依赖范围 测试compile范围 时间角度

![complie和provided比较](./images/032_a_compile_provided.png)  

* 从时间角度看，`compile`范围的依赖会部署到服务器中。而`test`和`provided`范围的依赖不会部署到服务器中。

## 033 Maven 命令行 实验六 依赖范围 测试test范围

![在main中导入junit](./images/033_a_import_junit_in_main.png)  

* 若在main中导入junit类，可以看到编译报错。

![执行编译报错](./images/033_b_run_compile_command.png)  

* 从时间角度看，生成后的war包里也不会包含关于`test`范围的内容。

## 034 Maven 命令行 实验六 依赖范围 测试provided范围

![结论](./images/034_a_summary.png)  

## 035 Maven 命令行 实验七 依赖传递性

![依赖的传递](./images/035_a_dependency_transfer.png)  

![测试依赖的传递](./images/035_b_test_dependency_transfer.png)  

* 在java工程的`pom.xml`中添加如下依赖:
![java工程添加依赖](./images/035_c_update_pom_in_pro1.png)  

* 查看web工程依赖树，可以看到只有范围是`compile`的依赖传递了过来:
![查看web工程依赖树](./images/035_d_confirm_dependency_in_pro2.png)  

## 036 Maven 命令行 实验八 依赖的排除

![依赖的排除](./images/036_a_remove_dependency.png)  

* 在web工程的`pom.xml`中配置对`commons-logging`依赖的排除。

![配置依赖的排除](./images/036_b_remove_dependency_in_pom.png)  

* 配置依赖的排除后，可以看到web工程中对`commons-logging`的依赖已被排除。
![确认web工程中此依赖被排除](./images/036_c_removed_dependency.png)  

* 但此配置对Java工程中对`commons-logging`的依赖不会产生影响。
![确认Java工程中没有排除此依赖](./images/036_d_not_removed_dependency.png)  
