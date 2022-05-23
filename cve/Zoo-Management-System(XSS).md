# Zoo Management System - 'admin_name' Stored Cross-Site Scripting(XSS)

   
# Exploit Title: Zoo Management System - 'admin_name' Stored Cross-Site Scripting(XSS)
# Exploit Author: webraybtl@webray.com.cn inc
# Vendor Homepage: https://www.sourcecodester.com/php/15347/zoo-management-system-source-code-php-mysql-database.html
# Software Link: https://www.sourcecodester.com/download-code?nid=15347&title=Zoo+Management+System+source+code+in+PHP+with+MySQL+Database
# Version: Zoo Management System 1.0
# Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.Zoo Management System does not filter the content correctly at the "content" module, resulting in the generation of stored XSS.

#### Payload used:
`<script>alert(111)</script>`

#### Proof of Concept

1. Login the CMS. 
Admin Default Access:
Email: admin@mail.com
Password: Password@123

1. Open Page http://172.24.5.102/zoo/admin/public_html/view_accounts?type=zookeeper and click Edit button

2. Put XSS payload  (`<script>alert(111)</script>`) in the content box and click on Edit Account to publish the page

![image](https://user-images.githubusercontent.com/60683449/169768692-dcd12bb1-5538-417d-bbe7-64bb0819d67b.png)
   

4. Viewing the successfully published page,We can see the alert.
![image](https://user-images.githubusercontent.com/60683449/169768724-96806218-54ae-47a4-a5a4-a1f274f0cb1a.png)

