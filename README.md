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

Any file upload and get shell：

Get administrator permissions:

![login](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E7%99%BB%E5%BD%95%E7%95%8C%E9%9D%A2.png)
![bp](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/bp%E7%88%86%E7%A0%B4.png)

Modify configuration:

![config1](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9D%83%E9%99%90%E7%AE%A1%E7%90%86-%E5%9F%BA%E6%9C%AC%E9%85%8D%E7%BD%AE.png)
![config2](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E4%BF%AE%E6%94%B9%E8%BF%90%E8%A1%8C%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E7%B1%BB%E5%9E%8B.png)

Any file upload:

![upload](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9C%A8%E9%A9%AC%E6%88%90%E5%8A%9F%E4%B8%8A%E4%BC%A0.png)

Conditional restrictions: Uploaded files do not have executable permissions by default, so there are many conditional restrictions on the exploitation of this vulnerability. In order to achieve vulnerability exploitation, we manually grant it permissions:

![ps1](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E6%97%A0%E6%89%A7%E8%A1%8C%E6%9D%83%E9%99%90.png)
![ps2](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%89%8B%E5%8A%A8%E8%B5%8B%E4%BA%88%E6%9D%83%E9%99%90.png)

Modify the extender configuration in the system:

![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E9%85%8D%E7%BD%AE%E6%9C%A8%E9%A9%AC.png)

Calling the calibre e-book converter can trigger the trojan to execute. Go online msf:

![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E8%A7%A6%E5%8F%91%E6%9C%A8%E9%A9%AC%E6%89%A7%E8%A1%8C.png)

Process before trojan call:

![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9C%A8%E9%A9%AC%E6%89%A7%E8%A1%8C%E5%89%8D%E8%BF%9B%E7%A8%8B.png)

The process after the trojan is called:

![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E6%9C%A8%E9%A9%AC%E6%89%A7%E8%A1%8C%E5%90%8E%E7%9A%84%E8%BF%9B%E7%A8%8B.png)

Trojan online msf:

![](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/%E4%B8%8A%E7%BA%BFmsf.png)
