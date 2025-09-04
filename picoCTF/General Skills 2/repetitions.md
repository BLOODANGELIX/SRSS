## Descripción del reto
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/477/enc_flag).

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/477/enc_flag
--2025-09-03 17:49:23--  https://artifacts.picoctf.net/c/477/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.72, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag                            100%[==================================================================>]     349  --.-KB/s    in 0s      

2025-09-03 17:49:23 (93.3 MB/s) - 'enc_flag' saved [349/349]

BLOODANGELIX-picoctf@webshell:~$ cat enc_flag 
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbHBWV0VKVVZGWmFWMDVHV2tkYVNHUlZDazFyY0ZkVWJGWlhZVlpLU0dWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
BLOODANGELIX-picoctf@webshell:~$ cat enc_flag | base64 -d
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlpVWEJUVFZaV05GWkdaSGRVCk1rcFdUbFZXYVZKSGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
BLOODANGELIX-picoctf@webshell:~$ cat enc_flag | base64 -d | base64 -d
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFZUXBTTVZWNFZGZHdU
MkpWTlVWaVJHeEVXbm93T1VOblBUMEsK
BLOODANGELIX-picoctf@webshell:~$ cat enc_flag | base64 -d | base64 -d | base64 -d
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aYQpSMVV4VFdwT2JVNUViRGxEWnowOUNnPT0K
BLOODANGELIX-picoctf@webshell:~$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZa
R1UxTWpObU5EbDlDZz09Cg==
BLOODANGELIX-picoctf@webshell:~$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfZGU1MjNmNDl9Cg==
BLOODANGELIX-picoctf@webshell:~$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
## Notas

base64 -d : sirve para transformar de Base 64 a ASCII.
## Referencia
