# Troubleshooter

## Issue about certificate verify failed

### Error

When:
```
source /home/gipsy/GipsyX-2.1/rc_GipsyX.sh && update_GipsyX_files.py -u
```
We get:
```
2025-06-12 11:58:12 ERROR: <urlopen error [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: self-signed certificate in certificate chain (_ssl.c:992)>
```

### Solution

in ` update_GipsyX_files.py`:
```
< import ssl

136,138c135
<     context = ssl._create_unverified_context()
<     with urllib.request.urlopen(url, context=context) as urlFid:
---
>     with urllib.request.urlopen(url) as urlFid:
```