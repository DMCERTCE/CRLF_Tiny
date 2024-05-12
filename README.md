# CRLF_Tiny

A CRLF vulnerability (%0D%0A) exists in TinyWeb Server creating a potential risk for redirection, XSS and other cool tricks depending on how the client interprets the HTTP Response. 
![image](https://github.com/DMCERTCE/CRLF_Tiny/assets/168325622/a75e6e91-e9c5-4bad-ad42-c7373cb7c842)

This vulnerability also leads to integrity failure, as logfiles can be spoofed:

Example:
http://localhost/%20HTTP/1.1"%0A8.8.8.8%20-%20-%20[12/May/2024:06:51:01 +0200]%20"POST%20/fakenews.html
Results in access_log in application directory:
![image](https://github.com/DMCERTCE/CRLF_Tiny/assets/168325622/5a899a48-4bb5-4df8-8016-7b0db04fbeb3)
Same most likely evident for agent_ and referer_ logs etc.

