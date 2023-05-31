# BeipyVideoResolution system exists in XSS vulnerability unauthorized in admin/admincore.php

#### Exploit Title: BeipyVideoResolution system exists in XSS vulnerability in admin/admincore.php
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://github.com/Beipy/BeipyVideoResolution
#### Software Link: https://github.com/Beipy/BeipyVideoResolution
#### Version: BeipyVideoResolution system V2.6
#### Tested on: Windows Server 2008 R2 Enterprise, Apache
#### Description
Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.Product Show Room Site does not filter the content correctly at the "admin/admincore.php" module, resulting in the generation of stored XSS.
1. vulnerability source code

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/36450a45-e133-4f68-b8f4-e749fddb3661)

2. request a post data and response 200 status_code,vulnerability variable in aik[gonggao]

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/c2dc9e82-c0c4-45b0-817f-60d510ccf9c0)




3. Request website homepage
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/d6e18c57-7575-4a3e-b830-d9d4ff473806)
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/d720c8a4-72b6-4efe-8809-dc66cfd6f8b2)

