# VIP-video-analysis system exists in SSRF vulnerability unauthorized in data/title.php

#### Exploit Title: VIP-video-analysis system exists in SSRF vulnerability in data/title.php
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://github.com/yiwent/Vip
#### Software Link: https://github.com/yiwent/Vip
#### Version: VIP-video-analysis system 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache
1. vulnerability source code

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/252b9b54-5a02-4606-a548-a295a1e0ce26)


2. request an incorrect port，response flase

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/b309e7f8-d129-4b17-9f21-0db4b8915cbf)


3. request an correct port，response true

![image](https://github.com/Xor-Gerke/webray.com.cn/assets/60683449/715e2881-3439-4931-b856-aa87e17e8413)
