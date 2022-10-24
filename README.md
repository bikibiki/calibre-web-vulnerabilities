# calibre-web-vulnerabilities
some vulnerabilities in calibre-web

JavaScript could get executed in a "Identifiers value" field and Arbitrary malicious link insertion.

After inserting and saving the xss payload, you need to check the page elements, and click the xss payload on the right to trigger the pop-up window.

![xss inject](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/inject-xss.png)
![alert](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/alert.png)

A denial of service in a "Trusted Hosts" field.

The payload is such as :  
```
<iframe οnlοad=alert("xss");></iframe>
<img src=1 οnerrοr=alert("xss");>
";!-"<XSS>=&{()}
maybe more payload could cause this problem.
```

![dos-payload](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/dos-payload.png)
![dos](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/dos.png)

any file upload and get shell：

获取管理员权限：
![login](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E7%99%BB%E5%BD%95%E7%95%8C%E9%9D%A2.png)
![bp](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/bp%E7%88%86%E7%A0%B4.png)

修改配置：
![config1](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9D%83%E9%99%90%E7%AE%A1%E7%90%86-%E5%9F%BA%E6%9C%AC%E9%85%8D%E7%BD%AE.png)
![config2](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E4%BF%AE%E6%94%B9%E8%BF%90%E8%A1%8C%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E7%B1%BB%E5%9E%8B.png)

任意文件上传：
![upload](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9C%A8%E9%A9%AC%E6%88%90%E5%8A%9F%E4%B8%8A%E4%BC%A0.png)

条件限制：上传的文件默认是不具有可执行权限的，所以该漏洞的利用也存在较多的条件限制，为了实现漏洞利用，我们手动赋予它权限：
![ps1](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E6%97%A0%E6%89%A7%E8%A1%8C%E6%9D%83%E9%99%90.png)
![ps2](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%89%8B%E5%8A%A8%E8%B5%8B%E4%BA%88%E6%9D%83%E9%99%90.png)

在系统中修改拓展程序配置：
![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E4%BF%AE%E6%94%B9%E8%BF%90%E8%A1%8C%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E7%B1%BB%E5%9E%8B.png)

调用calibre电子书转换器即可触发木马上线，上线msf：
![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E8%A7%A6%E5%8F%91%E6%9C%A8%E9%A9%AC%E6%89%A7%E8%A1%8C.png)

木马调用前的进程：
![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9C%A8%E9%A9%AC%E6%89%A7%E8%A1%8C%E5%89%8D%E8%BF%9B%E7%A8%8B.png)

木马调用后的进程：
![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9C%A8%E9%A9%AC%E6%89%A7%E8%A1%8C%E5%90%8E%E7%9A%84%E8%BF%9B%E7%A8%8B.png)

木马上线msf：
![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E4%B8%8A%E7%BA%BFmsf.png)
