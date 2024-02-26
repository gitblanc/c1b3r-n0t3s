# Investigate image metadata
- Use command `file image.png`
- Use command `exiftool image.png`
- Use command `xxd image.png`
- Use command `strings image.png`
- Use tool binwalk to search binary images for embedded files and executable code: `binwalk image.png`
	- To extract the file: `binwalk -e image.png`
- Use command: `steghide extract -sf image.png`
- [Steganographic Decoder](https://futureboy.us/stegano/decinput.html)
	- Upload the file to it
- Bruteforce the password and extract contents of an image:

```shell
stegseek -sf image.png /path/to/wordlist
# Then if it extracts something do
file whatever.file # to know what is it
```


