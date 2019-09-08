# StephanosTaekwondo
The project is implemented using Spring, Rest API and Oracle through which the instructur(user) can keep track track of his/her hundreds of students.

Steps to run the system:

1.	Install Eclipse IDE for Java EE Developers with JDK 8
Download ink: https://www.eclipse.org/downloads/ 

2.	Install maven on Windows
Installation link: https://www.mkyong.com/maven/how-to-install-maven-in-windows/ 

3.	Install odbc8.jar with maven in eclipse
For that use command : mvn install:install-file -Dfile=path of odbc8 jar file -DgroupId=com.oracle -DartifactId=ojdbc8 -Dversion=12.2.0.1 -Dpackaging=jar (in command prompt)

4.	Install Oracle 12c
Download link: https://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html 
Create user and grant all privileges in Oracle by following commands in cmd:
   1.	SQLPLUS
   2.	create user <username> identified by “<password>”; (e.g. user: home, password: orcl)
   3.	grant <privilege> to <user>; 
 
5.	Install Sql Developer
  Download link: https://www.oracle.com/technetwork/developer-tools/sql-developer/downloads/index.html 
  In SQL Developer on the left panel: Right click on Connections  New Connection
  In New/Select Database Connection prompt, enter details as follows:
    1.	Connection name: your connection name e.g. homeuser
    2.	Username: the user created in oracle i.e. home (in our example)
    3.	Password: password of oracle user i.e orcl
    4.	Select SID: orcl
    5.	Test & Connect

6.	Import the database file provided in SQL developer

7.	Import the project (StephanosTaekwondo) & angular project in eclipse workspace

8.	Install Node.js at same location of project in eclipse workspace using command: npm (in command prompt)
Download link: https://nodejs.org/dist/v10.16.0/node-v10.16.0-x64.msi 
  Next, 
  In eclipse IDE, Go to Run->Run Configurations and in Goals enter: tomcat7:run
  Update two files in the project:
    1.	Go to src->main->resources->db.properties and change the following:
        mysql.user=home
        mysql.password=orcl (the one created as oracle user)
    2. pom.xml (if tomcat server does not run, change port at line 108)

9.	There is one file student.service.ts from where Rest API is called by Anguar from Sping MVC framework. Make sure to use port used by tomcat (one in pom.xml) their. 

10. Run angular project at particular port specified in cmd after npm command in step 7 as: localhost:port-by-cmd/ e.g. localhost:4700/ in browser.


Project Description: 

- There is only one instructor who teaches all classes and he is the only user.
- Student data are stored in the database. This includes: their name, date of birth, the date they joined the school, their mobile number, email, and address.
- The school wants to track also the students’ parents (Mother and Father). Most students live with their parents but NOT all students have parents (some students might be adults so there is no need to keep track of their parents). We need to store also parents’ mobile phone and email address. Parents may also be students.
- 
