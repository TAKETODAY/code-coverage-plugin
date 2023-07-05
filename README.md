# 多模块 Jacoco 覆盖率合并工具

## 使用方式

在根配置文件配置：

```xml

<build>
  <plugins>

    <plugin>
      <groupId>org.eluder.coveralls</groupId>
      <artifactId>coveralls-maven-plugin</artifactId>
      <dependencies>
        <dependency>
          <groupId>jakarta.xml.bind</groupId>
          <artifactId>jakarta.xml.bind-api</artifactId>
          <version>2.3.3</version>
        </dependency>
      </dependencies>
      <configuration>
        <jacocoReports>${project.build.directory}/jacoco/jacoco.xml</jacocoReports>
      </configuration>
    </plugin>

    <plugin>
      <groupId>cn.taketoday</groupId>
      <artifactId>code-coverage-plugin</artifactId>
      <version>${revision}</version>
      <configuration>
        <!--put parent dir-->
        <destFile>${project.parent.build.directory}/jacoco/jacoco-unit.exec</destFile>
        <formats>XML</formats>
        <append>true</append>
      </configuration>

      <executions>
        <execution>
          <goals>
            <goal>prepare-agent</goal>
          </goals>
        </execution>

      </executions>

    </plugin>
  </plugins>
</build>
```

## 🙏 鸣谢

* [Jetbrains](https://www.jetbrains.com/?from=https://github.com/TAKETODAY/today-infrastructure): 感谢 Jetbrains 提供免费开源授权

## 📄 开源协议

使用 [GPLv3](https://github.com/TAKETODAY/today-infrastructure/blob/master/LICENSE) 开源协议

