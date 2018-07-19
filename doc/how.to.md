##
- 1.编译本maven项目，执行  mvn install 安装到本地库
- 2..编辑你的项目目标文件夹里的maven pom文件
- 加入如下内容
```java
   <build>
        <plugins>
            <plugin>
                <groupId>org.mybatis.generator</groupId>
                <artifactId>mybatis-generator-maven-plugin</artifactId>
                <configuration>
                    <verbose>true</verbose>
                    <overwrite>true</overwrite>
                </configuration>
            <dependencies>
                <dependency>
                    <groupId>com.my.tool.db</groupId>
                    <artifactId>mybatis-lombok-plugin</artifactId>
                    <version>1.0</version>
                </dependency>
            </dependencies>
            </plugin>
        </plugins>
    </build>
    <dependencies>
        <dependency>
            <groupId>org.mybatis.generator</groupId>
            <artifactId>mybatis-generator-core</artifactId>
            <version>1.3.6</version>
        </dependency>
        </dependencies>

```
---
3. copy generatorConfig.xml 和 mybatis_generator.properties 两个文件到POM文件所对应的项目的资源路径下.
最后执行在Maven的plugnin里选择mybatis generator执行即可