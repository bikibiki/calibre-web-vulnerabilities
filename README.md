# calibre-web-vulnerabilities
some vulnerabilities in calibre-web

JavaScript could get executed in a "Identifiers value" field and Arbitrary malicious link insertion.

After inserting and saving the xss payload, you need to check the page elements, and click the xss payload on the right to trigger the pop-up window.

![xss inject](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/inject-xss.png)
![alert](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/alert.png)

A denial of service in a "Trusted Hosts" field
![dos-payload](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/dos-payload.png)
![dos](https://github.com/bikibiki/calibre-web-vulnerabilities/blob/main/images/dos.png)
