# Home Clean Services Management System add_register.php File Upload Getshell

   
#### Exploit Title: Home Clean Services Management System add_register.php File Upload Getshell
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://www.sourcecodester.com/php/15293/home-clean-service-free-source-code.html
#### Software Link: https://www.sourcecodester.com/download-code?nid=15293&title=Home+Clean+Service+System+in+PHP+Free+Source+Code
#### Version: Home Clean Services Management System 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
At the file upload function, the application system checks the validity of the file type, format, and content uploaded by the user, so that attackers can upload Webshell (.php, .jsp, asp, etc.) malicious script files or files in unexpected formats, such as: HTML files, SHTML files, etc., at the same time, you can use characters such as directory jump or control the upload directory to directly upload files to the Web directory or any directory, which may lead to the execution of arbitrary malicious script files on the remote server, thereby directly obtaining application system permissions.Home Clean Services Management System does not filter the content correctly at the "register" module, resulting in the generation of File upload.

#### Payload used:
`<?php phpinfo();?>`

#### Proof of Concept

1. Login the CMS. 
Admin Default Access:
Email: admin
Password: admin

1. Open Page http://172.24.5.102/HCS/public_html/register.php?link=registerand

2. Put phpinfo payload  (`<?php phpinfo();?>`) in the images content and click on Register to publish the page
![image](https://user-images.githubusercontent.com/60683449/169929676-a097022d-e498-4570-85a9-8d405cb8d709.png)
![image](https://user-images.githubusercontent.com/60683449/169929709-ffca43db-7576-4e72-a399-f8ef36280918.png)


4. Viewing the successfully published page,Open Page http://172.24.5.102/HCS/public_html/uploads/8036-test.php ,We can see the phpinfo.
![image](https://user-images.githubusercontent.com/60683449/169929729-3a40af7f-57b8-4fd8-bf07-a60301c81c2f.png)


