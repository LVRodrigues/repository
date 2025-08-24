# Repository

Repositório de pacotes publicados.

## Maven

Utilize como projeto pai em projetos Maven para usar o GitHub como gerenciador de pacotes.

```bash
cd maven/bom
mvn install
```

Crie um arquivo de configuração para o Maven se integrar ao GitHub durante as fases de download e upload dos pacotes (~/.m2/settings.xml):

```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                      http://maven.apache.org/xsd/settings-1.0.0.xsd">

  <activeProfiles>
    <activeProfile>github</activeProfile>
  </activeProfiles>

  <profiles>
    <profile>
      <id>github</id>
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
```
