# Client-Server-Architecture-Using-A-MySQL-Relational-Database-Management-System

Client-Server refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another.

In their communication, each machine has its own role: the machine sending requests is usually referred as "Client" and the machine responding (serving) is called "Server".

A simple diagram of Web Client-Server architecture is presented below:

<img width="781" alt="Capture d’écran 2023-01-21 à 02 18 40" src="https://user-images.githubusercontent.com/38444929/213831738-ef1d126a-d5b0-4a6a-b5f4-38f5d4e7b564.png">

In the example above, a machine that is trying to access a Web site using Web browser or simply ‘curl’ command is a client and it sends HTTP requests to a Web server (Apache, Nginx, IIS or any other) over the Internet.

If we extend this concept further and add a Database Server to our architecture, we can get this picture:

<img width="771" alt="Capture d’écran 2023-01-21 à 02 22 26" src="https://user-images.githubusercontent.com/38444929/213831854-f4113526-ff10-40d7-9ae3-260d6749737a.png">

In this case, our Web Server has a role of a "Client" that connects and reads/writes to/from a Database (DB) Server (MySQL, MongoDB, Oracle, SQL Server or any other), and the communication between them happens over a Local Network (it can also be Internet connection, but it is a common practice to place Web Server and DB Server close to each other in local network).

TASK – Implement a Client Server Architecture using MySQL Database Management System (DBMS). To demonstrate a basic client-server using MySQL Relational Database Management System (RDBMS), follow the below instructions

1/ Create and configure two Linux-based virtual servers (EC2 instances in AWS).

Create and configure two Linux-based virtual servers (EC2 instances in AWS).
``
Server A name - mysql server
``
Server B name - mysql client
``

2/ On mysql server Linux Server install MySQL Server software.

3/ On mysql client Linux Server install MySQL Client software.

4/ By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses. Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your ‘mysql client’.

5/ You might need to configure MySQL server to allow connections from remote hosts.

`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

Replace ‘127.0.0.1’ to ‘0.0.0.0’ like this:

<img width="569" alt="Capture d’écran 2023-01-19 à 17 47 54" src="https://user-images.githubusercontent.com/38444929/213837737-4be47884-69ea-415a-907c-820ed661693c.png">

6/ From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.

7/ Check that you have successfully connected to a remote MySQL server and can perform SQL queries:

`Show databases;`

8/ If you see an output similar to the below image, then you have successfully completed this project – you have deloyed a fully functional MySQL Client-Server set up. Well Done!

<img width="346" alt="Capture d’écran 2023-01-21 à 01 41 54" src="https://user-images.githubusercontent.com/38444929/213838326-eebfa506-58ca-405c-bbe8-e696f128e565.png">




