# Bill Of Materials

Configurações iniciais para projetos Java e Maven, utilizando o Github como repositório.

## Restrições

* Java 21
* Maven 3.9.10

## Como Usar

Edite o arquivo **pom.xml** dos projetos Maven para herdarem as configurações deste projeto.

    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
        <modelVersion>4.0.0</modelVersion>
        <parent>
            <groupId>io.github.lvrodrigues</groupId>
            <artifactId>bom</artifactId>
            <version>21.0.0</version>
        </parent>
    ...
