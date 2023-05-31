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

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/1f9d7b87-b958-472d-9bcb-1a6b810482ea)

2. request a post data and response 200 status_code,vulnerability variable in aik[gonggao]

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/c605f644-2e21-44f1-b04f-cbfbb4a60e07)




3. Request website homepage
![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/6ef6dec5-0e05-4b5f-b0c3-1d6ab367cbf9)

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/de83b351-914c-45c6-af54-0d65e7489c0e)

