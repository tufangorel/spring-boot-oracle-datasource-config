# spring-boot-oracle-datasource-config

**1-) Download ojdbc8 driver from oracle web site**

Could not find artifact com.oracle:ojdbc:jar:18.0.0 in central2

https://www.oracle.com/database/technologies/appdev/jdbc-ucp-183-downloads.html

"ojdbc8.jar"

**2-) Install oracle jdbc driver into local .m2 maven repository**

C:\Users\Tufan>mvn install:install-file -Dfile=C:/Users/Tufan/Downloads/ojdbc8.jar -DgroupId=com.oracle -DartifactId=ojdbc8 -Dversion=18.0.0 -Dpackaging=jar

[INFO] Installing C:\Users\Tufan\Downloads\ojdbc8.jar to C:\Users\Tufan\.m2\repository\com\oracle\ojdbc8\18.0.0\ojdbc8-18.0.0.jar
[INFO] Installing C:\Users\Tufan\AppData\Local\Temp\mvninstall5271470864250313861.pom to C:\Users\Tufan\.m2\repository\com\oracle\ojdbc8\18.0.0\ojdbc8-18.0.0.pom

[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS

**3-) Create a new user for oracle database and give access rights**

alter session set "_ORACLE_SCRIPT"=true;

create user CUST identified by "123456";

grant create session to CUST;

grant connect to CUST;

grant create table to CUST;

grant create sequence to CUST;

grant create trigger to CUST;


**4-) Run maven command to execute integration test and connect to oracle database 18 from spring boot application.**

> mvn clean install
