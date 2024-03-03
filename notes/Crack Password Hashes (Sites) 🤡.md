- Sites:
	- [crackstation](https://crackstation.net/)
	- [hashes.com](https://hashes.com/en/decrypt/hash)

- Using Hashcat:

```shell
hashcat -m 160 'e5d8870e5bdd26602cab8dbe07a942c8669e56d6:tryhackme' /usr/share/wordlists/rockyou.txt
```

- `-m` option is the kind of hash you are trying to break
	- Identify the kind of hash with [hash identifier](https://www.kali.org/tools/hash-identifier/)
	- [Check more hash formats on Hashcat official web](https://hashcat.net/wiki/doku.php?id=example_hashes)

