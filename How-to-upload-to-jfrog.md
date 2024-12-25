## how to upload artifacts to jfrog artifactory

my pom.xml as follow
```bash

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" 
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="
             http://maven.apache.org/POM/4.0.0 
             https://maven.apache.org/xsd/maven-4.0.0.xsd">
             
    <modelVersion>4.0.0</modelVersion>
    
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.7.12</version> <!-- Updated Spring Boot version -->
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    
    <groupId>com.valaxy</groupId>
    <artifactId>demo-workshop</artifactId>
    <version>2.1.4</version>
    <name>demo-workshop</name>
    <packaging>jar</packaging>
    <description>Demo project for Spring Boot</description>

    <properties>
        <!-- Update Java version to 17 -->
        <java.version>17</java.version>
        <maven-jar-plugin.version>3.2.0</maven-jar-plugin.version> <!-- Updated version -->
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter</artifactId>
        </dependency>
        
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

        <!-- GitHub API -->
        <dependency>
            <groupId>org.kohsuke</groupId>
            <artifactId>github-api</artifactId>
            <version>1.99</version>
        </dependency>
        
        <!-- Twitter4J Core -->
        <dependency>
            <groupId>org.twitter4j</groupId>
            <artifactId>twitter4j-core</artifactId>
            <version>4.0.7</version> <!-- Updated version -->
        </dependency>

        <!-- JUnit for Testing -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.13.2</version> <!-- Updated version -->
            <scope>test</scope>
        </dependency>
        
        <!-- Spring Boot Test Starter -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
            <exclusions>
                <exclusion>
                    <groupId>org.junit.vintage</groupId>
                    <artifactId>junit-vintage-engine</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>junit</groupId>
                    <artifactId>junit</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>org.junit.jupiter</groupId>
                    <artifactId>org.junit.jupiter.api</artifactId>
                </exclusion>
            </exclusions>
        </dependency>
        
        <!-- Mockito for Testing -->
        <dependency>
            <groupId>org.mockito</groupId>
            <artifactId>mockito-junit-jupiter</artifactId>
            <version>4.8.1</version> <!-- Specify version -->
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <!-- Spring Boot Maven Plugin -->
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
            
            <!-- Updated Maven Surefire Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>3.0.0-M7</version>
                <configuration>
                    <argLine>-Xmx2048m</argLine>
                    <!-- Optional: Other configurations -->
                </configuration>
            </plugin>

            <!-- Updated JaCoCo Maven Plugin -->
            <plugin>
                <groupId>org.jacoco</groupId>
                <artifactId>jacoco-maven-plugin</artifactId>
                <version>0.8.10</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>prepare-agent</goal>
                        </goals>
                    </execution>
                    <!-- Generate Report During Test Phase -->
                    <execution>
                        <id>report</id>
                        <phase>test</phase>
                        <goals>
                            <goal>report</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>

    <!-- Distribution Management for JFrog Artifactory -->
    <distributionManagement>
        <repository>
            <id>central</id>
            <name>ubuntu-releases</name>
            <url>http://172.18.166.193:8081/artifactory/maven-cloverInfotech-local</url>
        </repository>
        <snapshotRepository>
            <id>snapshots</id>
            <name>ubuntu-snapshots</name>
            <url>http://172.18.166.193:8081/artifactory/maven-cloverInfotech-local</url>
        </snapshotRepository>
    </distributionManagement>

</project>

```

# step:2
after that also update or create new file settings.xml in .m2 directory 
![image](https://github.com/user-attachments/assets/6676df14-c060-44fd-a9b0-da07faddd681)
settings.xml file as follow

```bash
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0" 
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 
                              https://maven.apache.org/xsd/settings-1.0.0.xsd">

    <!-- 
        Global Maven settings file.
        Typically located at ~/.m2/settings.xml
    -->

    <!-- Servers Configuration -->
    <servers>
        <!-- JFrog Artifactory Release Repository -->
        <server>
            <id>central</id>
            <username>admin</username>
            <password>Admin123</password>
        </server>

        <!-- JFrog Artifactory Snapshot Repository -->
        <server>
            <id>snapshots</id>
            <username>admin</username>
            <password>Admin123</password>
        </server>
    </servers>

    <!-- Optional: Profiles Configuration -->
    <!-- 
        Profiles can be used to activate certain settings under specific conditions.
        Uncomment and configure if needed.
    -->
    <!--
    <profiles>
        <profile>
            <id>artifactory</id>
            <repositories>
                <repository>
                    <id>central</id>
                    <name>Artifactory Releases</name>
                    <url>http://172.18.166.193:8081/artifactory/maven-cloverInfotech-local</url>
                    <releases>
                        <enabled>true</enabled>
                    </releases>
                    <snapshots>
                        <enabled>false</enabled>
                    </snapshots>
                </repository>
                <repository>
                    <id>snapshots</id>
                    <name>Artifactory Snapshots</name>
                    <url>http://172.18.166.193:8081/artifactory/maven-cloverInfotech-local</url>
                    <releases>
                        <enabled>false</enabled>
                    </releases>
                    <snapshots>
                        <enabled>true</enabled>
                    </snapshots>
                </repository>
            </repositories>
        </profile>
    </profiles>

    <activeProfiles>
        <activeProfile>artifactory</activeProfile>
    </activeProfiles>
    -->

    <!-- Optional: Mirrors Configuration -->
    <!-- 
        Mirrors can redirect repository requests to a different repository.
        Uncomment and configure if you want all repository requests to go through Artifactory.
    -->
    <!--
    <mirrors>
        <mirror>
            <id>artifactory</id>
            <mirrorOf>*</mirrorOf>
            <url>http://172.18.166.193:8081/artifactory/maven-cloverInfotech-local</url>
        </mirror>
    </mirrors>
    -->

    <!-- Optional: Proxies Configuration -->
    <!-- 
        Configure proxies if your network requires it.
        Uncomment and configure if needed.
    -->
    <!--
    <proxies>
        <proxy>
            <id>example-proxy</id>
            <active>true</active>
            <protocol>http</protocol>
            <host>proxy.example.com</host>
            <port>8080</port>
            <username>proxyuser</username>
            <password>proxypass</password>
            <nonProxyHosts>localhost|127.0.0.1</nonProxyHosts>
        </proxy>
    </proxies>
    -->

</settings>

```
# step
