# Introduction 
O SonarQube é uma plataforma de código aberto desenvolvida pela SonarSource para inspeção contínua da qualidade do código para executar revisões automáticas com análise estática do código para detectar bugs, 
code smells e vulnerabilidades de segurança 
 
# Getting Started
Passos para instalação e uso do sonar
1.  Installation process
2.  Software dependencies
 
# 1.    Installation process
1.  Definir recursos de memória para rodar o sonar
```
$ sysctl -w vm.max_map_count=262144
$ sysctl -w fs.file-max=65536
$ ulimit -n 65536
$ ulimit -u 4096
```
2.  Criar as pastas para passar dadados para os volumes
``` 
$ mkdir -p /app/sonarqube/conf
$ mkdir -p /app/sonarqube/data
$ mkdir -p /app/sonarqube/logs
$ mkdir -p /app/sonarqube/extensions
$ mkdir -p /app/sonarqube/extensions/plugins
$ mkdir -p /app/sonarqube/postgres
$ chmod 777 /app/sonarqube -R
```
Inserir o arquivo sonar.properties na pasta /app/sonarqube/conf para ao rodar o docker compose o arquivo seja levado para dentro do container
 
3.  Baixar os plugins no diretório /app/sonarqube/extensions/plugins
``` 
wget https://github.com/SonarSource/SonarTS/releases/download/2.1.0.4359/sonar-typescript-plugin-2.1.0.4362.jar
 
wget https://github.com/SonarSource/SonarJS/releases/download/6.1.0.11503/sonar-javascript-plugin-6.1.0.11505.jar
 
wget https://github.com/SonarSource/sonar-dotnet/releases/download/8.0.0.9566/sonar-csharp-plugin-8.0.0.9566.jar
 
wget https://github.com/SonarSource/sonar-dotnet/releases/download/8.0.0.9566/sonar-vbnet-plugin-8.0.0.9566.jar
 
wget https://github.com/SonarSource/SonarJS/releases/download/6.1.0.11503/sonar-javascript-plugin-6.1.0.11505.jar
 
wget https://github.com/SonarSource/sonar-css/releases/download/1.1.1.1010/sonar-css-plugin-1.1.1.1010.jar
 
wget https://github.com/edwinyangzh/sonar-java-i18n-checks/releases/download/v0.1.0/java-i18n-rules-0.1.0.jar
 
wget https://github.com/SonarSource/sonar-xml/releases/download/1.4.3.1017/sonar-xml-plugin-1.4.3.1017.jar
 
wget https://github.com/mc1arke/sonarqube-community-branch-plugin/releases/download/1.1.1/sonarqube-community-branch-plugin-1.1.1.jar
 
wget https://github.com/SonarSource/sonar-ldap/releases/download/2.2-RC3/sonar-ldap-plugin-2.2.0.601.jar
```
 
4.  Rodar o docker composer
``` 
$docker-composer -p sonarqube up -d 
```
 
# 2.    Software dependencies
- docker
- docker compose