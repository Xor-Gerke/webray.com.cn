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

![image](https://github.com/user-attachments/assets/c4ecba1c-5041-4f43-9d86-30429e2cc7f6)

![image](https://github.com/user-attachments/assets/73a1f072-6a18-4eb6-8409-e8ad95828f8f)

Write a user Delivery Address

change HTML address-name Maxlength 

![image](https://github.com/user-attachments/assets/a68d052b-0701-4ccb-9a48-a3bc4ca573a3)


XSS-Payload :  `<img src=x onerror=alert(String.fromCharCode(88,83,83));>`

![image](https://github.com/user-attachments/assets/7885f64d-249c-4358-b95f-8738a791ed83)

