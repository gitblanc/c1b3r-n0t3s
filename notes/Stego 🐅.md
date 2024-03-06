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

- Use command `steghide info image.png`

- Inspect audio files (like `.wav` files) with [Sonic Visualizer](https://www.sonicvisualiser.org/)
	- Click on `Layer > Add Spectrogram`

![](img/Pasted%20image%2020240306215008.png)

- Now set the scale to dB^2 and the colour to White on Black

![](img/Pasted%20image%2020240306215637.png)

- Try with the tool [outguess](https://github.com/crorvick/outguess) when you have an image
	- Also there is this other project  (manteined) [outguess](https://github.com/resurrecting-open-source-projects/outguess)
	- Then, install it with: `./configure && make`
	- Then, try the command: `./outguess -r /file/to/analyze /path/to/the/output`
