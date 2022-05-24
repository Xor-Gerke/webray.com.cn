# Home Clean Services Management System Stored Cross-Site Scripting(XSS)

   
#### Exploit Title: Home Clean Services Management System Stored Cross-Site Scripting(XSS)
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://www.sourcecodester.com/php/15293/home-clean-service-free-source-code.html
#### Software Link: https://www.sourcecodester.com/download-code?nid=15293&title=Home+Clean+Service+System+in+PHP+Free+Source+Code
#### Version: Home Clean Services Management System 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.Home Clean Services Management System does not filter the content correctly at the "register" module, resulting in the generation of stored XSS.

#### Payload used:
`<script>alert(111)</script>`

#### Proof of Concept

1. Login the CMS. 
Admin Default Access:
Email: admin
Password: admin

1. Open Page http://172.24.5.102/HCS/public_html/register.php?link=registerand click Edit button

2. Put XSS payload  (`<script>alert(111)</script>`) in the content box and click on Register to publish the page
![image](https://user-images.githubusercontent.com/60683449/169929450-c9d5a51a-74d7-482f-b285-997fa10e1e70.png)
![image](https://user-images.githubusercontent.com/60683449/169929468-0674b395-3a29-4f6c-ae25-de2fe7091508.png)


   

4. Viewing the successfully published page,Open Page http://172.24.5.102/HCS/public_html/admin/userlist.php,We can see the alert.

![image](https://user-images.githubusercontent.com/60683449/169929484-386e7e6e-954c-4de2-9c42-569da21260e3.png)
