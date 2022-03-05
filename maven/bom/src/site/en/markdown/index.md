# Bill Of Materials

Initial configurations for Java and Maven projects, using Github as a repository.

## Restrictions

* Java 17
* Maven 3.8.4

## How To Use

Have the configuration file **~/.m2/settings.xml** changed to use GitHub as a package repository.

    <?xml version="1.0" encoding="UTF-8"?>
    <settings   xmlns="http://maven.apache.org/SETTINGS/1.0.0"
                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                                    http://maven.apache.org/xsd/settings-1.0.0.xsd">

        <activeProfiles>
            <activeProfile>github</activeProfile>
        </activeProfiles>

        <profiles>
            <profile>
            <id>github</id>
            <repositories>
                <repository>
                <id>central</id>
                <url>https://repo1.maven.org/maven2</url>
                </repository>
                <repository>
                <id>github</id>
                <url>https://maven.pkg.github.com/lvrodrigues/repository</url>
                <snapshots>
                    <enabled>true</enabled>
                </snapshots>
                </repository>
            </repositories>
            </profile>
        </profiles>

        <servers>
            <server>
            <id>github</id>
            <username>GITHUB_USERNAME</username>
            <password>GITHUB_ACCESS_TOKEN</password>
            </server>
        </servers>
    </settings>

After the initial configuration, the entire Maven project can inherit the settings from this build project by adding at the beginning of the configuration file (pom.xml) the declaration of using this project as Parent.

    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
        <modelVersion>4.0.0</modelVersion>
        <parent>
            <groupId>io.github.lvrodrigues</groupId>
            <artifactId>bom</artifactId>
            <version>17.0</version>
        </parent>
    ...
