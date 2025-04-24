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